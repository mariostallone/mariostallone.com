---
author: mariostallone
comments: true
date: 2012-10-26 14:51:42+00:00
layout: post
slug: design-patterns-state-pattern
title: Design Patterns - State Pattern
wordpress_id: 105
categories:
- Design Patterns
- General
- Technology
- Tips
tags:
- design patterns
- minesweeper
- state pattern
---

So I've decided to explore the state pattern first. State Pattern is defined as follows



<blockquote>Allow an object to alter its behaviour when it's internal state changes. The object will appear to change its class.</blockquote>



To illustrate this I'm going to use the classic MineSweeper as an example. Fr those of you who aren't familiar with the MineSweeper game, here's a brief intro.

**MineSweeper**
There is a grid of squares. Some do these squares have underneath them, mines and some of them are empty. The objective of the game is to uncover all the empty spots. Once a mine has been opened, the game ends with the mine blasting the entire field. Once an empty spot is uncovered, beneath a number, indicating the number of mines immediately neighbouring it is printed.

So, I'm going straight into the games implementation.

[![20121026-201051.jpg](http://mariostallone.com/blog/wp-content/uploads/2012/10/20121026-201051.jpg)](http://mariostallone.com/blog/wp-content/uploads/2012/10/20121026-201051.jpg)

The above diagram indicates that a Class **MineField** will hold many Spots, which could be either of type **MineSpot** or of type **EmptySpot**.
There is a different behaviour associated with the opening of a **MineSpot** and an **EmptySpot**. The common interface **Spot** from which both these classes are _inheriting_, enforces a method **open**. So, when a **MineSpot** is sent the message **open**, it will end the game blasting the entire **MineField**, and when an **EmptySpot** is open, it will uncover it, revealing the number of **mines** neighbouring it.
We've made use of a common type and associated different classes to perform a different action based on its type. That's how the **State Pattern** can be employed.

Simple, wasn't it? But, yet it saves us loads of effort and most importantly makes our code much cleaner, more manageable and of course, more extendable.
