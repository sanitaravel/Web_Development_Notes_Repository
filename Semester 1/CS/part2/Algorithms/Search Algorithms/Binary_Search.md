# Binary Search

- [Binary Search](#binary-search)
  - [Example: Searching a Star Catalog](#example-searching-a-star-catalog)
  - [Describing Binary Search](#describing-binary-search)
    - [Key Questions for Algorithm Implementation](#key-questions-for-algorithm-implementation)
  - [Binary Search Explanation](#binary-search-explanation)
    - [Using Variables for Reasonable Guesses](#using-variables-for-reasonable-guesses)
  - [Step-by-Step Description of Binary Search](#step-by-step-description-of-binary-search)
    - [Refining the Description](#refining-the-description)
  - [Understanding Binary Search on a Sorted Array](#understanding-binary-search-on-a-sorted-array)
    - [Checking if a Number is Prime](#checking-if-a-number-is-prime)
    - [Why Binary Search is Faster](#why-binary-search-is-faster)
    - [Writing Binary Search in Pseudocode](#writing-binary-search-in-pseudocode)
    - [Handling Missing Numbers](#handling-missing-numbers)

> Binary search is an efficient algorithm for finding an item in a sorted list. It works by repeatedly dividing the portion of the list that could contain the item in half until the possible locations are narrowed down to just one. Binary search was demonstrated in the guessing game in the introductory tutorial.

## Example: Searching a Star Catalog

One common use of binary search is to find an item in an array. For instance, the Tycho-2 star catalog contains information about the brightest 2,539,913 stars in our galaxy. Suppose you want to search the catalog for a particular star by name. Using a **linear search**, where the program examines every star sequentially, it could take up to 2,539,913 comparisons in the worst case. However, if the catalog is sorted alphabetically by star names, binary search would need to examine no more than 22 stars, even in the worst case.

## Describing Binary Search

When explaining an algorithm to someone, an incomplete description might suffice. For example, a cake recipe may skip obvious steps like opening the fridge to get eggs or cracking them. While humans can intuitively fill in these gaps, computer programs require fully detailed instructions.

### Key Questions for Algorithm Implementation

To implement an algorithm in a programming language, you need to understand it fully:

- **Inputs:** What data does the algorithm need?
- **Outputs:** What result should the algorithm produce?
- **Variables:** What variables are required, and what are their initial values?
- **Steps:** What intermediate computations are necessary to reach the final result?
- **Repetition:** Are there repeated steps that could use a loop?

## Binary Search Explanation

The main idea of binary search is to maintain a range of possible guesses. For example, if you are playing a guessing game where the number is between 1 and 100:

- Suppose you guess 25, and I tell you the number is higher.
- Then, you guess 81, and I tell you the number is lower.
- At this point, the only reasonable guesses are between 26 and 80.

In each step, you guess the midpoint of the current range of reasonable guesses:

- If the guess is incorrect, you eliminate half of the possibilities based on whether the guess is too high or too low.
- For instance, if the range is 26 to 80 and you guess 53, and I tell you 53 is too high, the new range becomes 26 to 52.

### Using Variables for Reasonable Guesses

To track the range of reasonable guesses:

- Let the variable `min` represent the current minimum reasonable guess.
- Let the variable `max` represent the current maximum reasonable guess.
- The input to the problem is `n`, the highest possible number. (For simplicity, we assume the lowest possible number is 1, though this can be modified.)

---

## Step-by-Step Description of Binary Search

Here’s how to use binary search in the guessing game:

1. **Initialize:**  
   Set `min = 1` and `max = n`.

2. **Make a Guess:**  
   Guess the midpoint of `min` and `max`, calculated as:  
   $\text{guess} = \left\lfloor \frac{\text{min} + \text{max}}{2} \right\rfloor$

3. **Check the Guess:**  
   - If the guess is correct, stop. You found the number!  
   - If the guess is too low, update `min` to one greater than the guess:  $\text{min}=\text{guess} + 1$
   - If the guess is too high, update `max` to one less than the guess: $\text{max} = \text{guess} - 1$

4. **Repeat:**  
   Return to step 2 until the number is found.

### Refining the Description

The above description can be made even more precise by:

- Clearly defining the inputs and outputs.
- Clarifying terms like "guess a number" and "stop."

## Understanding Binary Search on a Sorted Array

> Binary search is a way to quickly find an element in a sorted array. While JavaScript (and other programming languages) has built-in methods to search arrays, implementing it yourself helps you understand how it works.

Here’s an array of the first 25 prime numbers, sorted in order:

```javascript
var primes = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97];
```

### Checking if a Number is Prime

Let’s say we want to know if 67 is a prime number. If 67 exists in the `primes` array, then it’s prime.  

We might also want to know how many primes are smaller than 67. This can be determined by finding 67’s position in the array, which is called its **index**.  
For example:

- If 67 is at index 18, there are 18 smaller prime numbers in the array.  

> To find 67 using a **linear search**, we check each number one by one until we find it. However, this can take many steps if the array is large.  

### Why Binary Search is Faster

Binary search works by dividing the array into halves repeatedly until it finds the target number. It is much faster than linear search. Let’s see how it works step by step.

1. The array `primes` has 25 numbers, so the indices go from 0 to 24.  
   Start with `min = 0` and `max = 24`.  

2. Guess the middle index:  
   $`\text{guess} = \lfloor \frac{\text{min} + \text{max}}{2} \rfloor = \lfloor \frac{0 + 24}{2} \rfloor = 12`$

    Check `primes[12]` (which is 41).  

3. Is 41 equal to 67? No.  
   Since 41 is smaller than 67, the target must be to the right. Update:
   - `min = 12 + 1 = 13`
   - `max` stays 24.

4. Guess the new middle index:  
   $`\text{guess} = \lfloor \frac{13 + 24}{2} \rfloor = 18`$

   Check `primes[18]` (which is 67).  

5. We found the target! It only took two guesses instead of 19 steps (as in linear search).  

### Writing Binary Search in Pseudocode

> Here’s the basic idea of binary search, written in **pseudocode**:

1. Set `min = 0` and `max = n - 1` (where `n` is the array length).  
2. While `min` is less than or equal to `max`:
   - Calculate the middle index:  
     $
     \text{guess} = \lfloor \frac{\text{min} + \text{max}}{2} \rfloor
     $
   - If `array[guess]` equals the target, return `guess`.  
   - If `array[guess]` is less than the target, update `min = guess + 1`.  
   - Otherwise, update `max = guess - 1`.  
3. If the loop ends without finding the target, return `-1` (not found).  

### Handling Missing Numbers

If the target number isn’t in the array, binary search will narrow down the range until `min > max`. At this point, we know the number doesn’t exist, and we return `-1`.  

Here’s an updated version of the pseudocode:  

1. Set `min = 0` and `max = n - 1`.  
2. If `max < min`, return `-1` (target not found).  
3. Otherwise, calculate:  
   $`\text{guess} = \lfloor \frac{\text{min} + \text{max}}{2} \rfloor`$
4. If `array[guess]` equals the target, return `guess`.  
5. If `array[guess]` is less than the target, set `min = guess + 1`.  
6. Otherwise, set `max = guess - 1`.  
7. Repeat from step 2.  

Now, you’re ready to turn this pseudocode into an actual program using your favorite programming language!
