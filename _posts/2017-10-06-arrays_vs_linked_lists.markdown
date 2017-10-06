---
layout: post
title:      "Arrays vs Linked Lists"
date:       2017-10-06 05:03:25 +0000
permalink:  arrays_vs_linked_lists
---


Arrays and linked lists are commonly used to store lists of elements in memory. Although they have similar functions, they are stored in memory differently and are used for different scenarios.

Arrays must be stored in an unbroken sequence in memory, while elements in linked lists may be stored anywhere in memory. This makes adding elements to a linked list easier than adding them to an array, since there are less limitations. 

Each element in a linked list stores the address of the next item in the list. This makes it so that there is never a need to move the elements around. It is also useful for making efficient use of the space available.

Linked lists are useful for accessing the list in sequential order. Arrays on the other hand, are useful for when you want to access the list of elements in random order.

In arrays, the specific address for every item is already known from the start. You do not need to go through every element to find a specific cell, as you need to do for linked lists.

For example, if you would like to access the 7th element of an array, you can simply use its index to retrieve the element.

To get the 7th element in a linked list, you will need to go sequentially from the 1st element to retrieve the address of the 2nd element, then retrieve the address of the 3rd element from the 2nd element, and so on until you reach the 7th element.

When deciding between arrays and linked lists, it mainly comes down to the intended use.

Reading arrays and insertion in linked lists have a run time of O(1), while insertion in arrays and reading linked lists have a run time of O(n).
