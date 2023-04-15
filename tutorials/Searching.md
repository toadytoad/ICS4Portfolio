## Searching
Some computer programs need to find things in arrays and such. To do so, we implement searching algorithms. 

Searching algorithms locate the index of a given element within the array. There are two main methods of searching:

## Linear search
This searching algorithm works with any array, and simply loops through the entire array, comparing with its target value, and reports the index if it finds it.

The following java code implements this algorithm:

```java
int indexOf(int[] arr, int target){
  for(int i =0; i<arr.length; i++){
    if(arr[i]==target){
      return i;
    }
  return -1;
}
```


The algorithm is extremely quick to implement and returns -1 should the target value not exist in the array.

## Binary search

Let's play a game of guess the number, I'm thinking of a number between 1 and 100, and I will tell you if you're higher or lower. So what's your first guess? Well I bet it was 50! Seems like I've guessed your number now!
But why did you choose 50? Well choosing 50 splits the amount of numbers you need to try in half, as my response to it being above or below will eliminate half the numbers possible.
Binary search implements the same strategy when finding an element in a sorted list.

Binary search starts by looking at the middle element of the array, and comparing it with the target. If less than the target it will search in a similar fasion in the right half of the array, and will search in the left side of the array should it be greater than the target.
Binary search continues to do this until it either finds the element, or determines that the target is not in the list.

The following java code implements binary search:

```java
int binarySearch(int[] arr, int target){
  int h = arr.length-1;
  int l = 0;
  
  while(l<h){
    int m = (h+l)/2
    if(arr[m]==target) {
      return m;
    } else if(arr[m]<target) {
      l = m;
    } else {
      h=m;
    }
  }
  return -1;
```
