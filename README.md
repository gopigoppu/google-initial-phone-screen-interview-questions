# google-initial-phone-screen-interview-questions
Google Initial Phone Screen Interview Questions

**Google Interview Questions**

**1. Merge Sort**

Merge sort is a comparison-based sorting algorithm that employs the divide-and-conquer strategy. In the divide-and-conquer approach, the problem is divided into multiple subproblems, solved individually, and finally, the result of the subproblems are combined to form the final solution.

In merge sort, we divide the array into two smaller subarrays of equal size or with a size difference of one, depending on the parity of the array’s length. Each subarray is further divided into two smaller subarrays again and again recursively until we get subarrays of size one. We then sort the subarrays and merge them to produce the sorted array.

![Merge Sort Before](./images/merge_sort_1.png)
![Merge Sort After](./images/merge_sort_2.png)

<br>

**2. Quicksort**


Quicksort is a comparison-based sorting algorithm. Like merge sort, this is also based on the divide-and-conquer strategy. The algorithm has two basic operations —  swapping items in place and partitioning a section of the array.

Quicksort sorts an array by choosing a pivot element and then partitioning the rest of the elements around the pivot. All the elements less than the pivot are moved to the left side of the pivot (called left partition), and the elements greater than or equal to the pivot are moved to the right of the pivot (called right partition).

The sorting is continued on left and right partitions separately and recursively by choosing pivot points and breaking down the partitions into single-element subarrays before combining them to form one sorted list.

![Merge Sort After](./images/quick_sort.png)

<br>

**3. Key Differences Between Quicksort and Merge Sort**

**Functionality**

Although both merge sort and quicksort work on the same divide-and-conquer principle, they handle the partition and sorting very differently. 

Merge sort partitions a list into two sublists of equal sizes (different in size by 1, when the size of the list is odd) and merges the sorted sublists optimally to form a sorted list. In contrast, quicksort doesn’t necessarily partition the list into sublists of equal size. The partition sizes may be of any size, depending on how we choose the pivot.

We can also observe that merge sort performs all the sorting during the process of merging while quicksort performs most of the sorting in the process of dividing.

**Sorting Method**

Merge sort is an external sorting method in which the data that is to be sorted can be stored outside the memory and is loaded in small chunks into the memory for sorting.

Quicksort is an internal sorting method, where the data that is to be sorted needs to be stored in the main memory throughout the sorting process.

**Application**

Merge sort is very efficient for sorting linked lists since linked lists cannot be randomly accessed, and in merge sort, we don’t require random access, while in quicksort, we need to randomly access elements.

Quicksort is very efficient for sorting small datasets. It is also the preferred sorting algorithm when allocating additional memory is costly since it is an in-place sorting algorithm while merge sort has a space complexity of O(n).

**Worst-Case Complexity**

Merge sort performs the same number of comparison and assignment operations for an array of a particular size. Therefore, its worst-case time complexity is the same as best-case and average-case time complexity, that is, O(n log n).

In quicksort, as we’ve already discussed, the choice of the pivot plays an important role. Let’s suppose we always choose the rightmost element of a list to be the pivot and the input array is reverse-sorted. The partitions created will be highly unbalanced (of sizes 0 and (n - 1) for a list of size n); that is, the sizes of the partitions differ a lot. This results in the worst-case time complexity of O(n2).

**What They Work Well On**

Merge sort operates well on any type of dataset, whether it is large or small.

Quicksort generally is more efficient for small datasets or on those datasets where the elements are more-or-less evenly distributed over the range.

**Speed**

Merge sort generally performs fewer comparisons than quicksort both in the worst-case and on average. If performing a comparison is costly, merge sort will have the upper hand in terms of speed.

Quicksort is generally believed to be faster in common real-life settings. This is mainly due to its lower memory consumption which usually affects time performance as well.

**Space Requirement**

Merge sort requires the creation of two subarrays in addition to the original array. This is necessary for the recursive calls to work correctly. Consequently, the algorithm must create n elements in memory. Thus, the space complexity is O(n). 
Merge-sort can be made in place, but all such algorithms have a higher time complexity than O(n log n).

Quicksort is an in-place sorting algorithm. Its memory complexity is O(1).

**Stability**

Merge sort is a stable sorting algorithm, i.e., it maintains the relative order of two equal elements.

Quicksort is an unstable sorting algorithm, i.e., it might change the relative order of two equal elements.

**Efficiency**

The characteristics of the list don’t affect the speed of merge sort. If we assume the time cost of comparison and assignment to be constant, merge sort always takes the same time for a particular size of an array. Thus, it is consistent and efficient on any kind of dataset.

The efficiency of quicksort largely depends on how we choose the pivot. If the partitions created are very unbalanced, quicksort becomes very slow and inefficient. However, in general, quicksort is very efficient for small datasets.

<br>

![Merge vs Quick Sort](./images/merge_vs_quick.png)

<br>

**4: Which is a better sorting algorithm — merge sort or quicksort?**

There’s no definite answer to this question. It really depends on the kind of data we want to sort and what kind of sorting we expect. Both the algorithms have their advantages and disadvantages.

Let’s just go through some scenarios for better understanding:

If we want the relative order of equal elements after sorting the data to be preserved, merge sort would be the preferred choice since merge sort is a stable sorting algorithm while quicksort isn’t. Although quicksort can be modified to be stable, it is hard to implement and reduces the algorithm’s efficiency.

If the cost of allocating new memory is very high, we should always prefer quicksort since it is an in-place sorting algorithm while merge sort requires additional memory. 

Although merge sort can be modified to work in-place, its efficiency would be reduced.
If the dataset to be sorted is too big to fit in the memory all at once, using quicksort wouldn’t be possible since it is an internal sorting algorithm and requires random access to the whole dataset during the process of sorting. Merge sort, being an external sorting algorithm, would serve the purpose in this case.

<br>

**5: Why is merge sort preferred over quicksort for sorting linked lists?**

Quicksort highly depends on randomly accessing the data elements and swap elements in the dataset. Since the memory allocation of linked lists is not necessarily continuous, we can not randomly access elements of a linked list efficiently. This also makes swapping very expensive in linked lists. Merge sort is faster in this situation because it reads the data sequentially. Data insertion in any part of the linked list is also very efficient if we are given the reference to the previous node so that the merge operation can be implemented in-place. Thus, merge sort becomes an ideal sorting algorithm for linked lists.

<br>

**6.Merge sort, advantages and disadvantages**

**Advantages**

* It is quicker for larger lists because unlike insertion and bubble sort it doesnt go through the whole list seveal times.

* It has a consistent running time, carries out different bits with similar  times in a stage.

**Disadvantages**

* Slower comparative to the other sort algorithms for smaller tasks.

* Goes through the whole process even i he list is sorted (just like insertion and bubble sort?)

* Uses more memory space to store the sub elements of the initial split list.

<br>

**7. What's the difference between external sorting and internal sorting?**

In internal sorting all the data to sort is stored in memory at all times while sorting is in progress. In external sorting data is stored outside memory (like on disk) and only loaded into memory in small chunks. External sorting is usually applied in cases when data can't fit into memory entirely.

So in internal sorting you can do something like shell sort - just access whatever array elements you want at whatever moment you want. You can't do that in external sorting - the array is not entirely in memory, so you can't just randomly access any element in memory and accessing it randomly on disk is usually extremely slow. The external sorting algorithm has to deal with loading and unloading chunks of data in optimal manner.

<br>

*External Sorting :*

External sorting is required when the data being sorted do not fit into the main memory of a computing device (usually RAM) and instead, they must reside in the slower external memory (usually a hard drive). External sorting typically uses a hybrid sort-merge strategy. In the sorting phase, chunks of data small enough to fit in main memory are read, sorted, and written out to a temporary file. In the merge phase, the sorted sub-files are combined into a single larger file.

* Merge sort
* Tape sort
* Polyphase sort
* External radix
* External merge

*Internal Sorting :*

Internal sorting are type of sorting which is used when the entire collection of data is small enough that sorting can take place within main memory. There is no need for external memory for execution of sorting program. 
It is used when size of input is small

* Bubble sort
* insertion sort
* quicksort
* heapsort