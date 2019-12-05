---
title: "Programming Bottom-Up"
weight: 1
# bookFlatSection: false
# bookShowToC: true
---

# Programming Bottom Up - Paul Graham

[(Original Article)](http://www.paulgraham.com/progbot.html)

## Disclaimer

In the original article, the concept of bottom-up programming is written in the concept of Lisp programming, a topic in which I have very little knowledge or experience in as if this writing. Therefore the summary below will mainly focus on the general concepts presented and might exclude any Lisp-specific mentions or points.

## Summary

### Introduction

Functional elements of a program should not be too large, otherwise it becomes incomprehensible and can easily conceal errors. It will be hard to read, hard to test, and hard to debug.

### How do you divide a program?

**Top-Down**

Top-down programming follow generally follow the following thought process:

"the purpose of the program is to do these seven things, so I divide it into seven major subroutines. The first subroutine has to do these four things, so it in turn will have four of its own subroutines"

This continues until the whole program has the right level of granularity (i.e. large enough do to something substantial, yet small enough to be understood as a single unit)

**Bottom-Up**

Changing the language to suit the problem. Used by experienced Lisp programmers.

Not only write your program down tow the language, but also build the language up toward your program. Language and program evolve together.

Ultimately, your program will look as if the language had been designed for it.

The higher you build up the language, the less distance you will have to travel from the top down to it.

> "It's worth emphasizing that bottom-up design doesn't mean just writing the same program in a different order. When you work bottom-up, you usually end up with a different program. Instead of a single, monolithic program, you will get a larger language with more abstract operators, and a smaller program written in it. Instead of a lintel, you'll get an arch."

### Benefits of Bottom-Up Programming

- Yield programs that are smaller and more agile as the language do more the work
- Promotes code re-use. Even across programs.
- Makes programs easier to read
- Clarify your idea about the program's design as it causes you to always be on the lookout for patterns in your code

### Applications in Other Languages

Bottom-up design is possible to a certain degree in other languages. It's happening whenever you see library functions

It's true that this style of development is better suited to programs which can be written by small groups. However, at the same time, it extends the limits of what can be done by a small group