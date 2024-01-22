The expression or variable’s resulting value must be of an integral or enumerated type. Examples of valid result types for switch-case expressions are `int`, `double`, `float`, and `char`. (Remember that characters, which have type `char`, are integral, because they have integer ASCII codes.) This statement will not be valid for expressions or variables that, for example, result in a string value.

```c
#include <stdio.h>

int main(){

  char grade = 'B';

  switch(grade){

    case 'A':

      printf("Excellent!\n");

      break;

    case 'B':

    case 'C':

      printf("Good job!\n");

      break;

    case 'D':

      printf("Okay, you passed.\n");

      break;

    case 'F':

      printf("Better try again...\n");

      break;

    default:

      printf("Invalid grade!!!\n");

  }

  printf("Your grade is %c\n", grade);

  return 0;

}
```