#CS107 

### Algorithms 
**What's an algorithm?**
An algorithm is a set of unambiguous instructions for solving a problem or sub-problem in a finite amount of data.

**Abstract Step**
An algorithmic step containing unspecified data.

**Concrete Step**
An algorithm step in which all details are specified.

### Arrays
An array is a homogeneous collection of items, in which an individual item is accessed by its position (index) within the collection.

Arrays have a **length**. As data is being read into an array, a counter is updated so that we always know how many data items were sorted.
The last index in the array is *length(array)-1*

### Algorithms on Arrays
As with most data, we will likely want to perform operations on an array.
**Usual ones:** creating, deleting, reading and writing content...
**More complex ones:** searching for an item, sorting them, reshaping them...

## Searching
There are many different approaches to searching, in this we will consider two main approaches:
- Sequential Search
- Binary Search

### Sequential Searching
A sequential search examines each item in turn and compares it to the one we are searching for.

If it matches, we have found the item. If not, we look at the next item in the array.
We stop either when we have found the item or when we have looked at all the items and not found a match

#### Sequential Search Example

```
SET position TO 0
SET found TO FALSE
WHILE (position < length(myArray) AND NOT found)
	IF (myArray[position] EQUALS searchItem)
		SET found TO TRUE
	ELSE
		SET position to position +1
RETURN found
```

![[Pasted image 20261123141416.png]]

![[Pasted image 20261123141427.png]]

#### Can we Improve Sequential Search?
We have two conditions for our while loop:
```
WHILE (position < length(myArray) AND NOT found)
```

Why: Upper bound on length of the array, so we don't go too far.

We could insert a copy of the value searched for after the last item, so a copy of the item is always found. 

Now the WHILE loop only has one condition to check and we know that if position == length(array) then the value wasn't in the original array.

This is called **sentinel.** It stands guard at the end of the array to make sure we don't go too far.

![[Pasted image 20261123141647.png]]

**Why do we need to check every element?**
In a sequential search, the algorithm must check every element in the worst-case scenario to conclusively prove that a target value is not present in the list. Because the data is typically unsorted, the algorithm has no structural information about where the target might be located, meaning it cannot safely skip any items.

**What about if we could guarantee that our array's contents were in a sorted order?**
If the array is sorted, you do not need to check every element.
You can use a much more efficient algorithm called **Binary Search**.
Instead of scanning from the beginning, binary search checks the middle element of the array. If the target value is smaller, it eliminates the upper half; if it is larger, it eliminates the lower half. This process of halving the search area repeats until the target is found, making it significantly faster than a sequential search. 

### Binary Search
Assume we have a sorted array.
Compare the value at the middle with the search term, either you find it or we eliminate half of the unexamined items.
The process is repeated on the half where the item **might be.**
We **subdivide** our problem (the search space) each time.

```
SET lower TO 0
SET upper TO length(myArray) - 1
SET found TO FALSE

WHILE (upper >= lower AND NOT found)
	SET middle TO (upper + lower) // 2
	IF (data[middle] EQUALS searchItem)
		SET found TO TRUE
	ELSE IF (data[middle] > searchItem)
		SET upper TO middle - 1
	ELSE
		SET lower TO middle +1
RETURN found
```

![[Pasted image 20261123142430.png]]
![[Pasted image 20261123142439.png]]

#### What is the complexity of this approach?
Binary search is more complicated than sequential search primarily because it requires the data to be sorted beforehand. Additionally, it relies on random access to elements (such as an array) rather than sequential access, making it inefficient for structures like linked lists.

**TODO: COMPLETE THESE NOTES! (missing content)**

### Sorting
**Sorting algorithms**
Algorithms that order the items in the collection based on the sort key.

**Stable Sorting Algorithms**
Algorithms that don't re-order sorted data.

**Comparison**
The ability to **compare** two elements is critical.

Comparing ordered sequential data is relatively intuitive:
... -1 < 0 < 1 < 2 ...
5=5

What about other types of data?
Student_A < Student_B ?

**Sorting**
Arranging items in a collection so that there is an ordering on one (or more) of the fields in the items.

**Sort Key**
The field (or fields) on which the ordering is based.

### Selection Sort
Given a list of values, put them in ascending order
- Find the value that comes first, and write it into a second array
- Delete the value from the original list
- Continue this cycle until all the values on the original list have and written into the second list, at which point the second list contains the same items but in sorted order.

Each time, we are **selecting** the smallest value to place into the current index.

>A slight adjustment to this approach does away with the need to duplicate space: Instead of writing the smallest value to a second list, exchange it with the value currently in the position where it should be placed.


![[Pasted image 20261123143644.png|500]]

```
SET currentIndex TO 0
WHILE (not sorted yet)
	FIND smallest unsorted item
	Swap currentIndex item with smallest
	SET currentIndex TO currentIndex + 1
```

```
SET currentIndex TO 0
WHILE (currentIndex < length(myArray))
	SET indexOfSmallest TO currentIndex
	SET index TO currentIndex + 1
	WHILE (index < length(myArray))
		IF (myArray[index] < myArray[indexOfSmallest])
			SET indexOfSmallest TO index
		SET index TO index + 1
	SWAP myArray[currentIndex] WITH myArray[indexOfSmallest]
	SET currentIndex to currentIndex + 1
```

### Swap
```
SET temp TO data[currentIndex]
SET data[currentIndex] TO data[indexOfSmallest]
SET data[indexOfSmallest] TO temp
```

