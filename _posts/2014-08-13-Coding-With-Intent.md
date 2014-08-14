---
published: false
---

## Coding With Intent

Hi.

In this blog post I'm going to outline a process I try to adhere to when I write code with the intent of solving a problem. This process has been directly extrapolated from a lecture entitled _Alogrithm of an Alogrithm_ given by Hack Reactor instructor Phillip Alexander. I'll describe this process in the context of the famous nQueens puzzle.

First, it helps to think about the question What is an Algorithm? Generally an algorithm can be thought of as a procedure that produces a result. We encounter alogithms everyday. A common example that everybody is familiar with would be a recipie in a cookbook. Here we have a specific set of instructions, the steps listed in the recipie, that operate on a given set of inputs, the ingredients, and produce a result, a chocolate cake perhaps.

Software engineers use and write alogrithims all the time to solve specific problems with code, but how do they come up with a given alogrithm? What would the steps be to write an alogrithm or as the title states, what is the _Alogrithm of an Alogrithm_?

**Step 1: Establish the Rules of the problem.**

This is the most basic step but sometimes, for me at least, the easiest to forget. The goal with step one is to define the domain of the problem in as specific terms as possible.

In order to define the domain, you need to establish the core components. A few diagnostic questions can assist this process:

What are the inputs and outputs? Understand what if anything you can put in and what the expected result looks like. For instance ask yourself am I being given a number, a string, an object or a function? What am I expected to return? Is it a number, or maybe an array? These questions can be applied to whole applications, modules or specifc functions.

**Step 1: nQueens.**

nQueens is a classic problem of Alogrithm design. The basic problem goes something like this. Given a number _n_, return the number of _n by n_ chessboards that exist with _n_ queens placed such that no queen can attack any other queen. So what are we trying to fugure out here?

This is a little abstract and can be difficult to imagine. We can help ourselves by applying some of the questions from above. Let's start with the inputs. What will we be given? In this case _n_ represents a _number_. If we pick a number, let's say 4, our problem can be restated like this: Given the number 4, return the number of 4 by 4 chessboards that exist with 4 queens placed such that no queen can attach any other queen. That's a little better.

Now what are we being asked to return? Again it is a number! This information is immensely helpful to us. We can expect a number and we will return a number. It sounds pretty basic, but this is critial to understand before we attempt to solve the problem. It gives us a specific target.

**Step 2: Write tests that verify a solution.**

Understanding what for the answer will take is useful. Know what a valid answer is invaluable. Here we are establishing the vlaidity of our result. Given a specific set of inputs, my result should be this.

Now if you're working in some branch of theoretical anything, this step might be a bit challenging, but the good news is most of us are not. You should be able to establish a base case of your problem that has a known result. This will help you determine the validity and reliability of your algorithm. In this context, reliability is the frequency that your solution will provide thae same result given the same inputs. Hint: it should be 100%. Validity is the abilty of your solution to produce correct results.

**Step 2: nQueens.**

We can write tests for our solution through _Test Driven Development_. TDD is a process by which you establish perfomance expectations for your project. Before you write any code you should write tests. Writing tests prior to writng code is one technique for doing a mental walkthrough of your application which helps solidify your thinking about how to write your code.

In most cases you don't understand all of the components of a system when you start thinking about it. Writing tests that describe the perfomance and behavior of your application allows you to go from vague sense of what you want to a specific sense of what you need. They are a great mechanism for giving you specific actionable tasks that contriute to the ultimate goal.

In addition to helping you plan out your development path, _TDD_ also give you a system for monitoring the impact of changes as your application grows. As you introduce new features or refactor code, your tests will tell you if you've compromised any existing functionality.

In a later blog post, I will detail installing atesting suite built aroung Mocha and Chai. We'll write tests for every aspect of our nQueens solver, planning out our approach to the solution along the way.

**Step 3: Explore the problem space.**

After establishing a good context for your problem, you can now start to think about any common patterns your problem may exhibit or contemplate any special edge cases you may need to handle.

Many problems exhibit similar traits: put things in order, find the lowest or largest, convert this to that, for each of these, apply this modification, etc. By identifying patterns you can reuse techniques that worked in similar situations.

Understanding what edge cases you'll have to handle or what base cases will result in a valid solution will also help you craft a solution. In many situations these can be the easiest scenarios to identify first and include or eliminate from your results accordingly.










