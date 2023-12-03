
## Write to a file 
```python
# Create a new file object
fileObject = open("my_newfile", "w") 
# Write a string to the file 
fileObject.write("This string will be written to the file.\n") 
# Close the file 
fileObject.close()
```
|Character|Meaning|
|:-:|---|
|`\\`|displays the character '\'|
|`\'`|displays the single quote (')|
|`\"`|displays the double quote (")|
|`\b`|backspace character|
|`\f`|[formfeed](https://en.wikipedia.org/wiki/Page_break)|
|`\n`|[linefeed](https://en.wikipedia.org/wiki/Newline)|
|`\r`|[carriage return](https://en.wikipedia.org/wiki/Carriage_return)|
|`\t`|[horizontal tab](https://en.wikipedia.org/wiki/Tab_key)|
|`\v`|[vertical tab](https://en.wikipedia.org/wiki/Tab_key)|
## Using with key word 
In this example, the variable _fileObject_ is available in the indent body of the statement. ==If we were to try and use the _fileObject_ outside the block then we would get an error as the file object has been closed and is now out of scope==
```python
# Open a file using the with feature 
with open("my_newfile", "w") as fileObject: 
	fileObject.write("This string will be written to the file \n")
```
## Read a File 
To read from a file, we must open the file for reading and then read each line of the file, line by line. We can read each line using a loop. The in the snippet below is a way of making the program loop forever and we break out of the loop using the keyword. This is required because we don't know how many lines are in the file.
```python
# Open a file using the with feature
with open("my_newfile", "r") as fileObject:
    while True:
        # Read a line form the file
        line = fileObject.readline()
        # If the line is empty break the while loop
        if line == "":
            break
        else:
            print(line)
```
## CSV - Comma separated value files

Comma separated value files (csv) are common in practice for transferring data between systems. As it is commonly used, Python has a module for working with csv files, appropriately name `csv`. ==The `csv` module provides a number of useful functions but we will only look at reading and writing csv files. ==The `reader()` function in the module returns a list for each line in the file, and the elements of the list are the values delimited by commas (we may specify an alternative delimiting character when we construct the reader). The `writer()` function in the module writes lists of values to a file, applying the correct formatting.

### Reading CSV files

Let’s look at a simple example of how to read a csv file. In this example, the module `csv` is imported and the `reader()` function is used.

```python
import csv
with open(filename) as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

### Writing CSV files

Let’s look at how to write to a csv file using the `writer()` function:

```python
import csv
monty_python = [['Title', 'Release Date'],
['And Now For Something Completely Different', '1971'],
['Monty Python And The Holy Grail', '1975'],
["Monty Python's Life Of Brian", '1979'],
['Monty Python Live At The Hollywood Bowl', '1982'],
["Monty Python's The Meaning Of Life", '1983']]

with open('test.csv', 'w') as file:
    writer = csv.writer(file)
    for film in monty_python:
        writer.writerow(film)
```

In this example we first create a list of lists (ie _montypython_) with the content to be written to a csv file. Using the `with` notation we create a new file object. The `writer = csv.writer(file)` creates a csv writer for the file object we just created. We can then loop through the elements in _monty_python_ using a `for` loop and write each element to the file using the `writerow()` method in csv writer. The method `writerow()` accepts a list and writes a comma-separated value entry to the file.