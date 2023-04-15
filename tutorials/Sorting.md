## Sorting
Often, we need to sort lists of data in order to get valuable information out of them. For example if we wanted the nth tallest person in a room, we would sort all the people by height, and count n people from the left.
Now, in real life, sorting can be done very fast just by eye, however it takes much longer for computers to sort numbers. There are many algorithms which exist that implement sorting, one of which is DropMergeSort.

## DropMergeSort

Several esoteric sorting algorithms exist, that are completely impractical by taking as much time as possible or ones that completely break the conventions of sorting. For example, Miracle Sort relies on cosmic rays targeting the computer's memory to cause bit flips until the array is sorted. Another example is formally named Drop Sort, but has also gotten the nicknames Stalin sort and Trump sort. Drop sort has a time complexity of O(N), despite the fastest sorting algorithm supposedly being O(NlogN). Drop Sort does so by removing all elements which are not in order (you might be able to see now why it’s gotten those nicknames). This yields a sorted array, but not the original array. Unlike Miracle Sort, Drop Sort still has some hope of being a useful sorting algorithm. In fact, I have devised an algorithm based on drop sort which runs in O(N√N).

## Pseudocode
The following sudocode describes the algorithm:

```
DropMergeSort:
Inputs: An array of numbers arr, a starting index L, originally set to 0.
Outputs: No output, sorts the array in place.
1. If L is equal to the length of the array, return.
2. Set P = L.
3. Set max to a minimum value.
4. For each element i in the array starting at index P, If i is greater than
max, swap i with that at index P, increment P, set max to i.
5. DropMergeSort(arr, P)
6. Merge the subarrays arr[L:P] and arr[P:].
(See https://en.wikipedia.org/wiki/Merge_algorithm)
```

## Time Complexity
The time complexity is extremely difficult to calculate. The size of a list after
being sorted using drop sort is expected to be the harmonic sum. Using this
fact it is possible to find the expected recursive depth of the sort. However,
with the method of swapping ordered elements in the unsorted part of the
array with the unordered elements, this creates an unsorted array which on

average is sorted much faster than a random array of the same size. For this
reason it is not viable to mathematically calculate the time complexity. The
second option to do so is to find average time measurements of how long
the algorithm takes to sort several arrays of varying size and plot them.
Then, using regression analysis, find a matching time complexity. By
guessing a polynomial time complexity, we can interpolate the time
measurements using a function of the form y = ax . This achieves a time b
complexity extremely close to O(N√N), with a correlation coefficient of
0.9995.
