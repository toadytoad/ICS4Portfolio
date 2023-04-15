## Too Many Variables!
What if I wanted to define a class of students of an arbitrary size? There's only so many variables I can define to store each student. The matter becomes worse when we take the class list from user input. 
How do we solve this problem? Arrays! Arrays can store a set amount of variables in them, and can be modified by indicating the position of the variable that you wish to modify.

## Coding Time
Create a driver class. In the driver's main method, create an array of integers:

```java
int[] arr = {/* any numbers of your choice here */}
```

To output the contents of the first element of an array, use the following code:

```java
System.out.println(arr[0])
```

The square brackets here indicate the index from which we are reading from. But why is that number 0 if we want the first element? This is called 0-indexing, and it indicates that the starting position of the array is 0, while the last is 1 less than the length of the array.
Continue testing the properties of arrays. How do you write values, how do you read values, if I want the last element of the array, how do I get the length of the array?
