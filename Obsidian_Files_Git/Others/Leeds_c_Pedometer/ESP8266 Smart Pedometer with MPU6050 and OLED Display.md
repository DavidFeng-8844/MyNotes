## **Introduction:**

 My project employs an innovative approach by harnessing the power of the ESP8266 microcontroller, an OLED screen, and the MPU6050 accelerometers. My method leverages data from all three axes, enabling an accurate step counts.

**Key Components:**
![[Weixin Image_20231213152746.jpg]]
> 1. **ESP8266 Microcontroller:**
     The ESP8266 serves as the central processing unit, facilitating real-time data acquisition and analysis.
>2. **OLED Screen:**
     The OLED screen provides a user-friendly interface for displaying step counts.
>3. **MPU6050 accelerometers:**
   The MPU6050 accelerometers is a pivotal component, capturing precise acceleration data along all three axes (X, Y, and Z).
---
## Video Display
1. Uploading the program 
![[2e72aeb498ed08b99e509b87e25566b0.mp4]]
2. ![[97eb67c26b1e330511fbb99e907ea529.mp4]]
## How It Works
![[Pasted image 20231213110915.png]]

The MPU6050 IMU has both 3-Axis accelerometer and 3-Axis gyroscope integrated on a single chip.

>The gyroscope measures rotational velocity or rate of change of the angular position over time, along the X, Y and Z axis. 

>On the other hand, the MPU6050 accelerometer measures acceleration in the same way as the ==ADXL345 accelerometer sensor. ==Briefly, it can measure gravitational acceleration along the 3 axes and using some trigonometry math we can calculate the angle at which the sensor is positioned. So, if we fuse, or combine the accelerometer and gyroscope data we can get very accurate information about the sensor orientation. 

>But for measuring the steps, we only need the data from the accelerometers.


## ESP8266 
To implement step counting, we can use the MPU6050 to gather motion data, process it to detect steps, and then use the ESP8266 to communicate this information through I2C,  which  is a synchronous serial communication protocol, meaning that data is transferred based on a shared clock signal between devices.
The image below show the functionalities of the ESP8266's pins. For I2C communication we should connect the SCL and SDA pin with the accelerator. 
- In Arduino programming for ESP8266, the `Wire` library is commonly used to handle I2C communication.
```c
#include "Wire.h
```

![[Pasted image 20231213110943.png]]




    
1. **Programmability:** The ESP8266 can be programmed using the Arduino IDE, Lua, or other programming languages. This makes it accessible to a wide range of developers and hobbyists.
    
3. **Flash Memory:** The ESP8266 typically comes with built-in flash memory for storing program code and data. The amount of flash memory can vary among different ESP8266 modules.
    
4. **Integration with Arduino:** The ESP8266 can be easily integrated with the Arduino platform, allowing users to leverage the Arduino IDE and its vast ecosystem of libraries and examples. Actually I am using the VScode plugin called platform IO to upload the code 
	And I can use Serial Monitor to receive the data from the single board. 
	![[Pasted image 20231213150139.png]]
	


---
---
## Algorithm
**Introduction:**


**[Displaying the Code: The Setup]**

- First things first, let's take a look at the setup. We've included the necessary libraries, such as Wire, MPU6050, SPI, Adafruit_GFX, and Adafruit_SSD1306 for communication and display functionalities.
```c
#include "Wire.h"

#include "MPU6050.h"

#include <SPI.h>

#include <Adafruit_GFX.h>

#include <Adafruit_SSD1306.h>
```
All these libraries can be downloaded from Github, Arduino official website  or Platform IO library
![[Pasted image 20231213150421.png]]



**[Variables and Constants]**

- I've defined several constants like `SAMPLE_RATE`, `WINDOW_SIZE`, and `SENSITIVITY` that play a crucial role in our step-counting algorithm.
- `FILTER_CNT` determines the number of samples used to calculate the average, and `THRESHOLD_CNT` sets the number of threshold values to consider.
```c
#define SAMPLE_RATE 10              /* Sample rate in ms */

#define P_P_DIFF 1000               /* Threshold value for the difference between maximum and minimum values of 3D data */ //defulat to 1000

#define FALLING_EDGE 0              /* Falling edge state */

#define FILTER_CNT 4

#define SAMPLE_SIZE 4

#define WINDOW_SIZE 300

#define MIN_WAIT 1000               /* Wait time between max and min  */

#define STEP_OK 8                   /* Number of consecutive valid steps */

#define SENSITIVITY 10000           /* Sensitivity of the sensor */

#define THRESHOLD_CNT 4

#define MAX(a,b) ((a) > (b) ? (a) : (b))

#define MIN(a,b) ((a) < (b) ? (a) : (b))
```

**[Algorithm Overview]**

- Now, let's dive into the algorithm itself. The core logic is based on detecting acceleration peaks within a given time window and analyzing them against a dynamic threshold.

**[Filtering and Averaging]**

- I use a filtering mechanism to collect data from the MPU6050 and calculate the average of the samples, smoothing out any noise.
- The function below take the sensor's data and update the data to the sample 
```c
void filter_calculate(filter_avg_t *filter, axis_info_t *sample) {

  // Read sensor data and apply filter

  for(int i = 0; i < FILTER_CNT; i++) {

    accelgyro.getMotion6(&ax, &ay, &az, &gx, &gy, &gz);

    filter->info[i].x = ax;

    filter->info[i].y = ay;

    filter->info[i].z = az;

  }

  unsigned int i;

  short y_sum = 0, z_sum = 0;

  int x_sum = 0;

  for (i = 0; i < FILTER_CNT; i++) {

    x_sum += filter->info[i].x;

    y_sum += filter->info[i].y;

    z_sum += filter->info[i].z;

  }

  sample->x = x_sum / FILTER_CNT;

  sample->y = y_sum / FILTER_CNT;

  sample->z = z_sum / FILTER_CNT;

}
```

**[Finding Extremes]**

- The `find_extremes` function identifies maximum and minimum values within a specified time window, allowing us to establish a dynamic threshold for step detection.
```c
threshold_t find_extremes(filter_avg_t *filter, axis_info_t *sample, threshold_t *threshold) {

  unsigned long window_start_time = GetTime();

  axis_info_t max_value, min_value;

  int sp_avr_min, sp_avr_max, cur_avr_max, cur_avr_min = 0;

  bool max_found, min_found = 0;

  

  //Initialize max and min values

  max_value.x = max_value.y = max_value.z = 0;

  min_value.x = min_value.y = min_value.z = 0;

  

  while (GetTime() - window_start_time < WINDOW_SIZE) {

    // Collect a sample

    filter_calculate(filter, sample);

    // Print test sample

    Serial.print("Test Sample: ");

    Serial.print(sample->x);

    Serial.print("\t");

    Serial.print(sample->y);

    Serial.print("\t");

    Serial.println(sample->z);

    // Find the maximum value

    if (sample->x > max_value.x) max_value.x = sample->x;

    if (sample->y > max_value.y) max_value.y = sample->y;

    if (sample->z > max_value.z) max_value.z = sample->z;

    //delay(SAMPLE_RATE); // Wait for the next sample

    //Compare the average maxium

    cur_avr_max = (max_value.x + max_value.y + max_value.z) / 3;

    sp_avr_max = (sample->x + sample->y + sample->z) / 3;

    // break the loop if the current maximum value is greater than the sample maximum value

    if (sp_avr_max < cur_avr_max) {

      max_found = 1;

      threshold->max[threshold->count] = max_value;

      break;

    }

  }

  // If the maximum value is found, find the minimum value

  // Find the minimum value for up to 1 second

  if (max_found) {

    while(GetTime() - window_start_time < WINDOW_SIZE + MIN_WAIT) {

      // Collect a sample

      filter_calculate(filter, sample);

      // Find the minimum value

      if (sample->x < min_value.x) min_value.x = sample->x;

      if (sample->y < min_value.y) min_value.y = sample->y;

      if (sample->z < min_value.z) min_value.z = sample->z;

      //delay(SAMPLE_RATE); // Wait for the next sample

      //Compare the average minium

      cur_avr_min = (min_value.x + min_value.y + min_value.z) / 3;

      sp_avr_min = (sample->x + sample->y + sample->z) / 3;

      // break the loop if the current minimum value is less than the sample minimum value

      if (sp_avr_min > cur_avr_min) {

        if (threshold->count >= THRESHOLD_CNT)  {

          // Reset the threshold count

          threshold->count = 0;

          threshold->min[threshold->count] = min_value;

          min_found = 1;

          threshold->count++;

          break;

        }

        min_found = 1;

        threshold->min[threshold->count] = min_value;

        threshold->count++; //Only update the threshold count wehn the minimum value is found

        break;

      }

    }

  }

  if (min_found = 1) {

    Serial.print("Average max & min: ");

    Serial.print(cur_avr_max);

    Serial.print("\t");

    Serial.println(cur_avr_min);

  } else {

    Serial.println("No Min Value found within one second.");

  }

  return *threshold; //return the current threshold value

}
```

**[Dynamic Threshold]**

- The dynamic threshold is a four-sample circular buffer that works in
	the same fashion as the low-pass filtering stage
- The dynamic threshold is crucial for sensitivity adjustments. If the difference between the maximum and minimum values exceeds the sensitivity threshold,  dynamic threshold will be updated

```c
int find_threshold (threshold_t * threshold) {

  // The dynamic threshold is updated every time the difference between the

  // maximum and the minimum is greater than the SENSITIVITY.

  

  //Initialize the variables every time before the loop

  int sum_avr_max = 0, sum_avr_min = 0;

  int max_avr, min_avr = 0;

  

  //Calculate the latest average maximum and minimum values for the three axis from the threshold buffer

  for (int i = 0; i < threshold->count; i++) {

    sum_avr_max += (threshold->max[i].x + threshold->max[i].y + threshold->max[i].z) / 3;

    sum_avr_min += (threshold->min[i].x + threshold->min[i].y + threshold->min[i].z) / 3;

  }

  max_avr = sum_avr_max / threshold->count;

  min_avr = sum_avr_min / threshold->count;

  //Test print

  Serial.print("buffer max & min: ");

  Serial.print(max_avr);

  Serial.print("\t");

  Serial.println(min_avr);

  //Update the cur_thd if the difference between max_avr and min_avr is larger thatn the sensitivity

  if (max_avr - min_avr > SENSITIVITY) {

    threshold->cur_thd = (max_avr + min_avr) / 2;

  }

  return threshold->cur_thd;

}
```


**[Detecting Steps]**

- Detecting the steps by comparing the current maximum and minimum values with the dynamic threshold, ensuring they meet specific criteria. If so,  increment the step count and return the  step count .
```c
int possible_step (int test_thd, threshold_t * threshold, int possibleStep) {

  int max_peak;

  int min_peak;

  

  // Compare the maximum and minimum values of the current sample with the dynamic threshold

  max_peak = (threshold->max[threshold->count].x + threshold->max[threshold->count].y + threshold->max[threshold->count].z) / 3;

  min_peak = (threshold->min[threshold->count].x + threshold->min[threshold->count].y + threshold->min[threshold->count].z) / 3;

  if (max_peak > test_thd + SENSITIVITY / 2.4 && min_peak < test_thd - SENSITIVITY / 4) {

    possibleStep++;

  }

  return possibleStep;

}
```
- - In the loop function, an algorithm considers that a person is walking or running if at least eight consecutive possible steps occur, which is an extra measure of the algorithm to avoid false positives due to isolated events, the ``walkStat``  is set to `true`  which certifies all eight previous possible steps as valid, and enters regulation mode. In this mode, every consecutive step is counted as valid. 

```c
void loop() {

  unsigned long currentStepCount = Step_Count(ax, ay, az); //Pass the values of the accelerometer to the step count function

  // the algorithm considers that a person is walking or running

  //if at least eight consecutive possible steps occur, which is an extra

  //measure of the algorithm to avoid false positives due to isolated

  //events

  if (currentStepCount > stepCount) {

    stepCount = currentStepCount;

    if (currentStepCount > STEP_OK) { //if the current step count is greater than 8

    if (!walkSta) {               //if the walk state is false

      walkSta = true;           //set the walk state to true

      lastTime = GetTime();     //set the last time to the current time

    }else {

      if (GetTime() - lastTime > 10000) {   //if the current time minus the last time is greater than 10 seconds

        walkSta = false;                  //set the walk state to false

      }else {

        walkSta = true;

        digitalWrite(LED_BUILTIN, HIGH);

        Serial.print("Step Count: ");

        Serial.println(stepCount);

        Serial.println("\t\t+++++++++++++++++++++++");

        Serial.print("|\n|\n");

        Serial.print("|\tStep Count:\t");

        Serial.println(stepCount);

        Serial.println("\t\t+++++++++++++++++++++++");

        // Display the step count on the OLED screen

        display.clearDisplay();

        display.setTextSize(1); // Normal 1:1 pixel scale

        display.setTextColor(SSD1306_WHITE); // Draw white text

        display.setCursor(0,28); // Start at top-left corner

        display.println("Step Count: ");

        display.println(stepCount);

        display.display();

      }

    }

    }else {

          walkSta = false;

    }      

  }

  else {

      digitalWrite(LED_BUILTIN, LOW);

  }

}
```

**[Display and Feedback]**

- Finally, I provide visual feedback on the OLED screen and the Serial Monitor, making it easy to track the step count in real-time.
- ![[Weixin Image_20231213143832.jpg]]

[Data Analysis]
 1. The image below is the data from the Serial Monitor when the accelerometers remain still, the test sample is the real time data output of the aaccelerometer. 
 2.  The average max & min is the data of current peak value calculate from the ==filtered data==. 
 3. The bufffer max & min is the peak value calculated from the ==Dyanamic Threshold==
![[Pasted image 20231213144230.png]]
2. When the difference between the maximum and the minimum are greater than the sensitivity, the threshold is updated and printed on the Serial buffer for testing 

 ![[Pasted image 20231213151333.png]]
3. If 8 consecutive steps are occurred, the step would be updated 
![[Pasted image 20231213151501.png]]
**[Conclusion]**

- And there you have it! An Arduino-based step-counting algorithm using the MPU6050 sensor. This project is a fantastic example of combining hardware and software to create a practical application.
    
- If you enjoyed this video, don't forget to like and subscribe for more exciting projects. Feel free to leave comments and questions below, and we'll see you in the next video!