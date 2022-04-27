---
title: Back to Basics - Clean Code Chapter Six 
date: 2022-04-12T19:17:04.795Z
description: Revisiting good practices reading Clean Code by Robert Martin
---

Chapter six covers objects and data structures. This chapter was awesome and presented a lot really useful information. Right off the bat we're introduced to some example code that highlights the difference between exposing implementation and hiding it. The important take away from this initial set of examples is that classes shouldn't just expose getters and setters and we call it a day - classes should hide that implementation behind interfaces that allow users to manipulate the data accordingly. That _is_ the single most important point from this chapter.

## Data/Object Anti-Symmetry
- Objects hide their data behind abstractions and expose functions to operate on that data.
- Data structures expose their data and have no meaningful functions.
  - I can't lie - this is not a distinction I thought about often but it makes total sense.
  - There is a major difference between an enum implementation (like in PHP where they aren't native) and an object class.
  - Both are useful in their own right but tend to be misused.
- Data structures make it easy to add new functions.
  - Classes that use the data structures can be updated freely and the data structures need not change.
- Objects are different - they make it easy to add new classes without changing existing functions.
  - If classes are implementing an interface it's easy to make may different polymorphic types.
  - However if you change the interface all the classes now have to change.
- Sometimes you do just want simple data structures with procedures operating on them.

## The Law of Demeter
- An object should not expose its internal structure through accessors because that exposes structure
- The law says that a method _f_ of a class _C_ should only call methods of:
  - _C_ (it's own class)
  - An object created by _f_ (you new up something in _f_ and now have access to it's instance methods)
  - An object passes as an argument to _f_
  - An object held in an instance variable of _C_
- This can be summed up as _talk to friends, not to strangers_

## Train Wrecks
- I've seen a lot of javascript that looks train wrecky
- The idea is that instead of long run on chain calling we're better off breaking up calls and assigning the results to variables.
- This relates to Demeter in that the calling function knows how to navigate through a lot of different objects _it knows too much_
- The example given (using function chain calling) would be better served as a data structure

## Hybrids
- This is what I was getting at when I said objects and data structures are useful but misused
- Sometimes you encounter half object and half data structure implementations
- They are the worst of both worlds and we should avoid

## Hiding Structure
- 

