---
layout: post
title: "Solving a Sudoku with AI"
date: 2017-02-14
categories: ['Artificial Intelligence']
---

[Sudoku](https://en.wikipedia.org/wiki/Sudoku) is one of the world's most popular puzzles. It consists of a 9x9 grid, and the objective is to fill the grid with digits in such a way that each row, each column, and each of the 9 principal 3x3 subsquares contains all of the digits from 1 to 9. The detailed rules can be found, for example, [here](http://www.conceptispuzzles.com/?uri=puzzle/sudoku/rules).

## Goals of this project

The main goal of this project is to build an intelligent agent that will solve every sudoku while introducing you to two powerful techniques that are used throughout the field of AI:

### Constraint Propagation 

When trying to solve a problem, you'll find that there are some local constraints to each square. These constraints help you narrow the possibilities for the answer, which can be very helpful. We will learn to extract the maximum information out of these constraints in order to get closer to our solution. Additionally, you'll see how we can repeatedly apply simple constraints to iteratively narrow the search space of possible solutions. Constraint propagation can be used to solve a variety of problems such as calendar scheduling, and cryptographic puzzles.

### Search 

In the process of problem solving, we may get to the point where two or more possibilities are available. What do we do? What if we branch out and consider both of them? Maybe one of them will lead us to a position in which three or more possibilities are available. Then, we can branch out again. At the end, we can create a whole tree of possibilities and find ways to traverse the tree until we find our solution. This is an example of how search can be used.

[![](/img/sudoku.png)](https://youtu.be/ETiHDwsZ9yQ) 


[Source Code](https://github.com/srikanthpagadala/udacity/tree/master/Artificial%20Intelligence%20Nanodegree/Solving%20a%20Sudoku%20with%20AI){:target="_blank"}

[Report](http://htmlpreview.github.io/?https://github.com/srikanthpagadala/udacity/blob/master/Artificial%20Intelligence%20Nanodegree/Solving%20a%20Sudoku%20with%20AI/report.html){:target="_blank"}

