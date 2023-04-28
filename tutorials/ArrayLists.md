## What if I've filled up my array?
Not to worry! ArrayLists have come to the rescue. ArrayLists support arbitrary sizes of arrays, to which you can continue adding elements. To create an ArrayList of Strings, use the following syntax:

```java
List<String> lst = new ArrayList<>();
```

They can also be created to have a given initial capacity, as well as initialize them with a copy of another Collection:

```java
List<Integer> bigList = new ArrayList<>(100000);
List<String> lstCopy = new ArrayList<>(lst);

With this list you may now add elements, remove elements, and so much more, as Java implements tons of useful methods that act on ArrayLists. Refer to the official Oracle JavaDocs on ArrayLists to explore more that ArrayLists can do.

An important note is that to create an ArrayList of built in datatypes, use the datatypes object counterpart. For example, isntead of int, using Integer, and instead of long, use Long.

Instance methods of ArrayLists:

```java
// Add an element to the end of the array
lst.add("Hello World!");

// Add an element at a given index
lst.add(0, "Hi!");

// Get an element by index
lst.get(1);

// Get size of list
lst.size();

// Set the element at a given index
lst.set(0, "Bye!");

// Remove from list
lst.remove(0);
```


[Home](../index.md)
