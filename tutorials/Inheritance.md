## A Hypothetical Scenario
Consider looking out at a city skyline. What do you see a lot of? Buildings!
Are all buildings the same? No. Some are shorter, while others are taller. Some are shaped differently. Some are different colours. But what they have in common is that they are still buildings.
What do all buidings have? An address, a height, and a number of rooms.
However, some buildings are designed to be functional for very specific things on top of these attributes.
For example, a hotel is very different from an office building. 
Let's use this as an example for how we inherit in Java.

## Coding Time

Create the classes Driver and Building. In the Building class, add 3 private instance variables and 3 methods to return a copy of the instance variables. The variables represent the buildings address, height, and rooms.
Add a constructor to the Building class which takes in 3 parameters to assign to each of the instance variables.

Now, if we wanted to create an office building, we could simply create a Building object, but we would lose everything that makes this building an office building.
Create the following class:
```java
public class OfficeBuilding extends Building{

}
```

Add any instance variables and methods you see fit.
For the constructor, every constructor starts with a call to the parent class constructor. You do this by calling `super()` with whatever parameters you wish. Then, you may continue to edit the variables in the OfficeBuilding class or the Building.
In the rest of your class, refer to `super` to access the Building class methods.

In your driver class, create two objects, one of type OfficeBuilding, and another of type Building. Test these two objects. What can you do in one that you can't do in the other? What can they both do?

Finally, complete the exercise by creating the Hotel class, which also extends the Building class. Add any instance veriable and methods that a hotel may posess but any other ordinary building may not.
Include a variable representing the number of vacant rooms in the hotel. What if we wanted the getter method for the number of rooms of the Building class to output the number of occupied and vacant rooms?
We can use overriding to do so. Simply redefine the getter method from the Building class, and implement the new program behaviour.

Continue experimenting with these 3 classes using the Driver class.

[Home](../index.md)
