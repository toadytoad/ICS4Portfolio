## Objects
Objects are exactly what you may think they are, simply things that exist and can do some other things, and interact with other objects.
When it comes to OOP, objects are at the core of its design patterns. To create an object, copy the following code into your Java IDE of choice:

```java
public class MyObject{

}
```

Create a driver class to use your objects:

```java
public class Driver{
    public static void main(String[] args){
    
    }
}
```

To create your first Object, add the following line to your main method in the driver class:

```java
MyObject obj = new MyObject();
```

Great! Now you have an object, but what can it do?

## Instance Variables
Instance Variables are information stored within an object. For example, a house class may store the house address, number of rooms, and any other relevant information about the house.
Instance variables can be considered private or public. Private variables can only be accessed the object itself, while an external force may read and edit public variables.
Add the following lines of code into your MyObject class:

```java
public String myString;
public int myPublicNum;
private int myPrivateNum;
```

In your Driver class, try printing these variables and assigning new values to them. What do the variables start at? What happened when you assigned new values to them and then printed them? Did you encounter any errors?

## Constructors
Notice how in the previous example, you encountered null values. So what if we wanted to assign values immediately to these variables before the Driver class even has a chance to access them?
To accomplish this, we use a constructor. Constructors do what it sounds like they do, they construct objects. Constructors can run code on the object before the owner of the object can use it.
Let's use a constructor to pass some values into our instance variables, add the following constructor to your MyObject class:

```java
public MyObject(String s, int n){
  this.myString = s;
  this.myPublicNum = n;
  /*
  YOUR OWN CODE HERE
  */
}
```

To refer to an instance variable, use the `this` keyword. Now add your own code to the constructor to assign a value to myPrivateNum. Test the new object using the Driver class. Does the program crash now that you've tried to access a private variable?

Next, let's add some functionality to our class:

## Instance Methods

Instance Methods are methods within a class which change the state of the object.
Add the following method to the MyObject class:

```
public void decrement(){
  this.myPrivateNum--;
}
```

Next implement the following instance methods:

1. A method to output the product of myPrivateNum and myPublicNum
2. A method to output myString
3. A method to increase myPrivateNum by a given value in the method parameters

Finally, use the Driver class to continue testing your object.

# Congratulations! You're well on your way to becoming an OOP master!
