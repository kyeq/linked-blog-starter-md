---
tags: [CS128, java-guide]
chapter: "Chapter 08 - Arrays and ArrayLists"
source: https://canvas.swansea.ac.uk/courses/68227/pages/arraylist-operations-the-most-useful-ones
---
#CS128 #java-guide

# ArrayList Operations - The Most Useful Ones
> [!info] From the CS-128 notes on Canvas — [open the original page](https://canvas.swansea.ac.uk/courses/68227/pages/arraylist-operations-the-most-useful-ones)

These are the most useful ArrayList operations - example programs are below.

//Assume we have an arraylist called 'listData'

- **listData.get(index)**  //return the item at location 'index'
- **listData.add(item)**  //insert 'item' at the end of the list
- **listData.add(index, item)**  //insert 'item' at location 'index'
- **listData.set(index, item)**  //replace 'item' at location 'index'
- **listData.size()**  //return the size of the array list
- **listData.isEmpty()**  //returns true if the list is empty
- **listData.contains(item)**  //returns true if 'item' is in the list
- **listData.indexOf(item)**  //the location of the *first* instance of 'item' - there could be more than one
- l **istData.lastIndexOf(item)**  //as above, but the last one - the same if there is only one
- **listData.clear()**  //empty the complete list
- **listData.remove(index)**  //remove the item at location 'index'
- l **istData.remove(item)**  //remove 'item' if present - returns true if it was present

---
← [[Memory Management (Ch 8)]] · [[Java Guide - Start Here|Contents]] · [[ArrayLists - Some Basic Operations (Ch 8)]] →
