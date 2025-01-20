# Bubble Sort

> **Bubble Sort** is one of the simplest sorting algorithms. It works by repeatedly comparing adjacent values in an array and swapping them if they are in the wrong order. The algorithm gets its name from the way the highest values "bubble up" to the top of the list.

- [Bubble Sort](#bubble-sort)
  - [How Bubble Sort Works](#how-bubble-sort-works)
  - [Manual Walkthrough of Bubble Sort](#manual-walkthrough-of-bubble-sort)
    - [Step-by-Step Example](#step-by-step-example)
  - [What Happens Next?](#what-happens-next)
  - [Visualizing Bubble Sort](#visualizing-bubble-sort)
  - [Key Points to Remember](#key-points-to-remember)

## How Bubble Sort Works

The Bubble Sort algorithm works as follows:

1. **Iterate Through the Array**: Start at the beginning of the array and look at each value one by one.
2. **Compare Adjacent Values**: Compare the current value with the next one.
3. **Swap If Necessary**: If the current value is greater than the next value, swap them to ensure the smaller value comes first.
4. **Repeat**: Go through the entire array multiple times, each time bubbling the next highest value to its correct position.

Here’s an example array we’ll sort using Bubble Sort:  
`[7, 12, 9, 11, 3]`

## Manual Walkthrough of Bubble Sort

Let’s go through one full pass of the algorithm step by step.

### Step-by-Step Example

1. Start with the unsorted array:  
   `[7, 12, 9, 11, 3]`

2. Compare the first two values (7 and 12).  
   Since 7 < 12, no swap is needed:  
   `[7, 12, 9, 11, 3]`

3. Move to the next pair (12 and 9).  
   Since 12 > 9, we swap them:  
   `[7, 9, 12, 11, 3]`

4. Move to the next pair (12 and 11).  
   Since 12 > 11, we swap them:  
   `[7, 9, 11, 12, 3]`

5. Move to the next pair (12 and 3).  
   Since 12 > 3, we swap them:  
   `[7, 9, 11, 3, 12]`

After this first pass, the largest value, 12, has bubbled up to its correct position at the end of the array.

## What Happens Next?

Even though the largest value (12) is in the right place, the rest of the array is still unsorted:  
`[7, 9, 11, 3, 12]`

The algorithm will now go through the array again, repeating the process:

- On the second pass, the second-largest value will bubble up to its correct position.
- On the third pass, the third-largest value will bubble up, and so on.

For an array with 5 values, Bubble Sort needs to run through the array 4 times to fully sort it.

## Visualizing Bubble Sort

Each pass through the array makes the unsorted portion smaller, as the highest values move to their correct positions. If you were to animate this, you would see the values "bubbling up" like bubbles rising in water.

## Key Points to Remember

- **Efficiency**: Bubble Sort is simple but not very efficient for large datasets. It has a time complexity of O(n²) for the worst case.
- **Best Use Case**: Bubble Sort is useful for small datasets or when simplicity is more important than speed.
- **How It Ends**: The algorithm stops when the entire array is sorted, meaning no swaps are needed during a pass.

By understanding these steps, you can now try implementing Bubble Sort in a programming language like JavaScript or Python!
