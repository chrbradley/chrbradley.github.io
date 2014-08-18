---
published: false
---

## Coding With Intent

Hi.

This blog post is kick's off a series that will venture through different aspects of software engineering with javascript. I'll present topics in context and application to the famous [nQueens puzzle](http://en.wikipedia.org/wiki/Eight_queens_puzzle "nQueens"). A variety of topics will be covered in this series including recursion, "this", instantiation patterns and test driven development.

To get started, I'm going to outline a process I try to practice when I write code with the intent of solving a problem. This process has been directly extrapolated from a lecture entitled _Alogrithm of an Alogrithm_ given by [Hack Reactor](http://www.hackreactor.com/ "Hack Reactor") instructor [Phillip Alexander](https://github.com/phillipalexander "Phillip Alexander").

First, it helps to think about the question What is an Algorithm? Generally an algorithm can be thought of as a procedure that generates a result. We encounter alogithms everyday. A common example that everybody is familiar with would be a recipie in a cookbook. Here we have a specific set of instructions, the steps listed in the recipie, that operate on a given set of inputs, the ingredients, and produce a result, a chocolate cake perhaps.

Software engineers use and write alogrithims all the time to solve specific problems with code, but how do they come up with a given alogrithm? What would the steps be to write an alogrithm or as the lecture title states, what is the _Alogrithm of an Alogrithm_?

**Step 1: Establish the Rules of the problem.**

This is the most basic step but sometimes, for me at least, the easiest to forget. The goal with step one is to define the domain of the problem in as specific terms as possible.

In order to define the domain, you need to establish the core components. A few diagnostic questions can assist this process:

What are the inputs and outputs? Understand what if anything you can put in and what the expected result looks like. For instance ask yourself what information am I being given. Is it a number, a word or group of words, an object or a function? What am I expected to return? Is it a number, or maybe a collection of items? These questions can be applied to whole applications, modules or specifc functions.

**Step 1: nQueens.**

nQueens is a classic problem of Alogrithm design. The basic problem goes something like this: Given a number _n_, return the number of _n by n_ chessboards that exist with _n_ queens placed such that no queen can attack any other queen. So what are we trying to fugure out here?

This is a little abstract and can be difficult to imagine. We can help ourselves by applying some of the questions from above. Let's start with the inputs. What will we be given? In this case _n_ represents a _number_. If we pick a number, let's say 4, our problem can be restated like this: Given the number 4, return the number of 4 by 4 chessboards that exist with 4 queens placed such that no queen can attach any other queen. That's a little better.

Now what are we being asked to return? Is it a set of valid solutions? Are we ment to count something or sort something? In this case, again it is a number! Having an awareness of this information is immensely helpful. Have you every started in on something, worked out a pretty sweet solution only to realize that it is invalid bacause it doesn't actually return the ouput as expected? It sounds pretty basic, but this is critial to understand before we attempt to solve the problem. It gives us a specific target.

**Step 2: Write tests that verify a solution.**

Understanding what form the answer will take is useful. Knowing what a valid answer is can be invaluable. Here we are establishing the vlaidity of our result. Given a specific set of inputs, my result should be this.

Now if you're working in some branch of theoretical anything, this step might be a bit challenging, but the good news is most of us are not. You should be able to establish a base case of your problem that has a known result. This will help you determine the validity and reliability of your algorithm. In this context, reliability is the frequency that your solution will provide thae same result given the same inputs. Hint: it should be 100%. Validity is the abilty of your solution to produce correct results.

**Step 2: nQueens.**

We can write tests for our solution through _Test Driven Development_. TDD is a process by which you establish perfomance expectations for your project. Before you write any code you should write tests. Writing tests prior to writng code is one technique for doing a mental walkthrough of your application which helps solidify your thinking about how to write your code.

In most cases you don't understand all of the components of a system when you start thinking about it. Writing tests that describe the perfomance and behavior of your application allows you to go from vague sense of what you want to a specific sense of what you need. They are a great mechanism for giving you specific actionable tasks that contriute to the ultimate goal.

In addition to helping you plan out your development path, _TDD_ also gives you a system for monitoring the impact of changes as your application grows. When you introduce new features or refactor code, your tests will tell you if you've compromised any existing functionality.

In a later blog post, I will detail the installation of a testing suite built around Mocha and Chai. We'll write tests for every aspect of our nQueens solver, planning out our approach to the solution along the way.

**Step 3: Explore the problem space.**

After establishing a good context for your problem, you can now start to think about any common patterns your problem may exhibit or contemplate any special edge cases you may need to handle.

Many problems exhibit similar traits: put things in order, find the lowest or largest, convert this to that, for each of these, apply this modification, etc. By identifying patterns you can reuse techniques that worked in similar situations.

Understanding what edge cases you'll have to handle or what base cases will result in a valid solution will also help you craft a solution. In many situations these can be the easiest scenarios to identify first and include or eliminate from your results accordingly.

This step should help you understand the problem domain allowing you to tailor your approach to the specific problem at hand.

**Step 3: nQueens.**

Let's take a moment to imagine how we may try to solve for a single solution of nQueens in real life. You have before you a real chesboard with a standard 8 x 8 layout of rows and columns totaling 64 possible spaces and 8 queens that you must place on the board so that none of them may attack another. What do you do first?

Your frist step will probably be to place a queen on a square. Which space at this point isn't important. Just think of it as Step One: Place queen 1. What would step 2 be? Again we need to place a queen, but in order to place it, we need make sure it isn't placed so that it can attack queen 1. You may elect to place it in the closest possible safe space or the farthest, again it doesn't matter. Step 2 could be restated as the following: Pick square, check to see if square can be attacked by queen 1, if it can be attacked pick a new square and check again, if it is safe, place queen 2. Placing the thrid queen would be the exact same process as step 2 with the exception that you now need to check against 2 attacking queens. Step 4 would have to consider 3 attacking queens and so on for all of our remaining queens.

This process can be described in a pattern: Pick square, check for conflicts, if none place queen, otherwise pick next square. We are effectively repeating the same steps over and over which is a classic example of a recursive problem.

For any given decision in our nQueens example, we can repeat the same decision making process. When you make one decision the remaining decisions look just like the previous but with a smaller set of data and every time we make a decision the problem set gets smaller and smaller until we have made the final decision. We can leverage this pattern to craft our solution. I will demonstrate an implementation of a recursive solution to nQueens in a future post.

**Step 4: Generate a simple plan that should solve the problem**

This step involves articulating a solution to the problem in plain old English. Step 3 above should gide you natrually into step 4, but it is helpful to seperate them mentally as distinct. Step 3 is more about trying to identify a problem type and step 4 is describing the steps you need to take in your natural language.

Here we want to be able to describe a specific plan of action before we attempt to implement it with working code. What do you want to happen and should it happen?

**Step 4: nQueens.**

We started to do this above in step three, but that was really just in an effort to identify any particular patterns that may be useful in solving our nQueens problem. Now we can attempt to describe what we want to happen and how we want it to happen:

It is important that we start with as simple a solution as possible here to give us the best chance of describing a coherent process. We can worry about optimizing later.

Our process may go something like this: Initialize the number of available queens. Place a queen on the board in the first column of the first row. Since she is the first, we don't need to check for any conflicts. Decrement the number of available queens by one. Place a new queen in the next available space and check for conflicts. If there is a conflict, pick her up and try the next space.

We've identified a step in our process here that might benefit from some elaboration: "check for conflicts". What does this really mean relative to our nQueens problem and does it describe an actionable step?

In chess Queens can attack opponents across any row, column or diagonal connected to the space they occupy. It would be a good idea to include this concept in our description in an effort to be specific in trying to articulate how our solution will work.

Picking up with our second queen, it may go like this: Place queen 2 in next available slot. Check for _row conflict_, if yes, move to the next spot. If not, check for _column conflict_, if yes move to the next spot. If not, check for _major-diagonal conflict_ ( up and behind through down and in front ). If yes, move to the next available space, if not check for _minor-diagonal conflict_ ( up and in front and down and behind ). If yes move to the next open space, if not place queen. Decrement available queens. Repeat until we've placed all of our queens or identified a conflict when trying to place a queen on the last space. 

This demonstrates the value in this exercise. By describing what we want to do in English, we idetified a vauge concept in our process. Checking for conflicts makes sense abstractly, but now we are starting to think about implementation. What does that really look like in terms of instructions for the computer? We've now got a more specific set of instructions that has brought us closer to an actionalbe code element.

**Step 5: Elaborate the steps into Pseudocode.**

This is first time that you should be in your program file. We've done a buch of groundwork which has hopefully resulted in a clear direction that will allow us to proceed with purpose. Now it's time to pseudo code.

Pseudo Code is the process by which we lay out our plan into steps that represent the heirarchies or structure of our program. It is where we begin to make our implmentation tangible.

So far I haven't mentioned anyting about functions or methods or variables or anything else related to a specific programming language. Everything we've done to this point has been language agnostic and pseudo should also be language agnostic. Good psuedo code can be adapted by any engineer into their language of choice.

**Step 5: nQueens**

This merits a dedicated post. 

**Step 6: Verify each step in the process for some simple input.**

This step is optional. Sometimes I'll record the progression of an input element as it flows through my pseudo code. This may be done with pen and paper or just a mental exercise. It is a dry run that can validate or invalidate aspects of the preperation thus far. It is a good mechanism for vetting the prep workleading upto this point.

**Step 7: Translate each step into code.**

Stay tuned...