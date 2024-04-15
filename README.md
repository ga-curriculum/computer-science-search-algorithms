# ![Search Algorithms](./assets/tktk-hero.png)

## Overview

In this module, students will learn how the binary search algorithm works to find information efficiently and elegantly.

## Learning Objectives

By the end of this lesson, you'll be able to:

  - Understand the Big O complexities of brute force and binary search approaches.
  - Describe how binary search works.
  - Write a binary search algorithm to find a value in an array.

## Prerequisites

  - Big O Notation
  - Recursion
  - Intro to Sorting Algorithms


## Time to complete

Estimated time to complete core lab exercise: **90 minutes**

### Search: It’s Been There All This Time

Programmers, when you were first taught arrays, your instructor most likely asked you to write code to find an element in an array. Or, maybe they asked you to write code to locate the index of an element in an array.

Let’s pretend you had to find the band “Def Leppard” in an array of hair metal bands.

Your final product may have looked something like this:
```javascript
// Determine if Def Leppard is in the array and find its index if so:
const hairMetal = ["Kiss", "Guns n Roses", "Van Halen", "Sammy Hagar", "Aerosmith", "Twisted Sister", "Motley Crue", "White Snake", "Poison", "Europe"]
let searchTerm = "Def Leppard"
let found = false;
let index = -1;
for(let i = 0; i < hairMetal.length; i++) {
  if hairMetal[i] === "Def Leppard" {
    found = true;
    index = i;
  }
}
if(found) {
  console.log(`${searchTerm} is located at index ${index} in the array`);
} else {
  console.log(`${searchTerm} not found`);
}
```

### And Then You Made it Better

As you were doing it, you probably realized that, once the element or index had been found, the computer didn’t need to keep searching for it. So, you added a break, or a statement that told the algorithm to stop looking for the element once it was located:

```javascript
for(let i = 0; i < arr.length; i++) {
  if arr[i] === "Def Leppard" {
    found = true;
    index = i;
    break;
  }
}
```

This means you were thinking about algorithmic complexity — making sure the algorithm didn’t keep running forever — even if you weren’t aware of it at the time. (Yes, Big O has always been haunting you.)

### And Then You Learned Array Methods

Later on, you probably discovered array methods like .indexOf(), .findIndex(), and .find() and learned to appreciate the elegance they added to your code:

```javascript
const hairMetal = ["Kiss", "Guns n Roses", "Van Halen", "Sammy Hagar", "Aerosmith", "Twisted Sister", "Motley Crue", "White Snake", "Poison", "Europe"]
// Locate Def Leppard in the array if it’s there:
const index = hairMetal.indexOf("Def Leppard"); // index === -1 because it wasn't found.

```

Your code was elegant indeed but not any more efficient. These methods are basically just fancy for loops, so the computer had to scan all the way through the array to know “Def Leppard” wasn’t there. 

### But What If I Told You...

That the array was already sorted?

Consider this: Would you rather try to find a word in a dictionary in which all of the words are alphabetized? Or one in which all of the words are in a totally random order?

If we sort our hair metal bands array alphabetically, we can leverage the computer’s special abilities:

```javascript
hairMetal.sort();
console.log(hairMetal)
// => ["Aerosmith", "Europe", "Guns n Roses", "Kiss", "Motley Crue", "Poison", "Sammy Hagar", "Twisted Sister", "Van Halen", "White Snake"]
// It's now sorted alphabetically!
```
### It Just Keeps Getting Better: Binary Search

With our newly sorted array, we can implement binary search to find a value. It’s similar to how we’d find a word in a dictionary — another nicely sorted array of values.

From a programming standpoint, it looks like this:

```javascript
Given a sorted array and a search value, 

    Find the middle element in the array. (If the array has an even number of elements, then take the one just left of center.)

    Did we get lucky — is this it?  

        Then, great!  We’re done!  

    If not,

        If the word we’re searching for comes before this middle element, 

            Search the subsection of the array from 0 to the element right before the middle element.

        Or, if it comes after this middle element,

            Search the subsection of the array from just to the element through to the end.
```
### Finishing the Search

Now it’s time to think about terminating our search. First, let’s update our algorithm a bit:

    If we’re down to a one-element array subsection and that element isn’t the one we want, we know the element isn’t there.
    If, after halving, we get down to an array of size 0, we know the element isn’t there.

“Def Leppard” is nowhere to be found. Our algorithm would return -1.

### Bringing Recursion to the Conversation

If you look at the process and diagrams from this example, you can see that binary search lends itself nicely to recursion. We’re performing the same logic on ever-shrinking parts of the array! So, let’s also add a little language to our algorithm that explicitly indicates our intent to use recursion on subsections of the array between specific start and end points.

(And yes, you could use a while loop here, too, but you know we love the slickness and elegance of recursion at times like these!)

```javascript
```



## Starter code

tktk If there is not a starter code repo that students will fork and clone to start this lab, then this section and all of its content should be removed.

🟢 [Starter code](#tktk-repository-for-starter-code)

## Content

- [Setup](./setup/README.md)
- [Exercise](./exercise/README.md)

## Level Up

🚀 [Level Up](./level-up/README.md) tktk - remove section if no level ups exist.

## Solution code

🏁 [tktk Solution code](#tktk-external-repo-link-url)

## Internal resources

✏️ [Instructor Guide](./internal-resources/instructor-guide.md)

🏗️ [Release Notes](./internal-resources/release-notes.md)

---

**Find a 👾 bug 👾 or have suggestions? [Let us know](https://git.generalassemb.ly/modular-curriculum-all-courses/universal-resources-internal/blob/main/module-feedback.md)!**
