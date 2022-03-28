---
title: Back to Basics - Clean Code Chapter Four 
date:  2022-03-24T18:23:46.782
description: Revisiting good practices reading Clean Code by Robert Martin
---

Chapter four of _Clean Code_ by Mr. Uncle Bob (as I've taken to calling him in my head) - covers commenting our code. This is a bit of controversial topic in my eyes. I fully understand and acknowledge the sentiment that 'good code is self documenting' - which is mostly the opinion expressed in chapter four; but I think some people make that statement too binary. Should we never comment things then? Is the addition of a comment ackowledging that our code is _bad_? Personally, I think no - comments are a good addition sometimes and they can exist in even good and expressive code. 

In the interest of acting with humility - I've been so guilty of a lot of these bad practices in the past. I think time has taught me when and when not to use comments and how to make them useful but let's see and get into the notes:

## Comments
- Mr. Uncle Bob hits us right out of the gate with _"comments are, at best, a necessary evil"_.
  - I think that goes a long way setting the expectation and tone for the rest of the chapter - _try to not write them_
  - I don't fully disagree with this
- Also - _"The proper use of comments is to compensate for our failure to express ourself in code"_.
  - I will take a bit of an exception to this statement.
    - I suppose if you are wrapping a lot of language logic in expressive function names this is expected to be the default state of things.
    - But, some times things just don't shake out this way. Maybe we're dealing with old code that violates a lot of the good practices we have discussed prior to this chapter. Maybe we are very limited on time or our team is adamant about how things should be structured. Point being - if you aren't in a green field situation of small functions and solid naming conventions then comments play a crucial role in productivity and understanding.
    - That being said - I think the remainder of the chapter does a _great_ job in laying out situations where comments can be useful and where they become pitfalls.
- Inaccurate comments are worse than no comments
  - Yep, I suppose that is a valid point. I can't argue that if comments are krufty and out of date they'll mislead very easily.
- Truth is always in code.
  - Yes, this is also true. And, some code is very very bad and hard to decipher. Splitting the difference - if there were some slightly out of date comments in bad code that help illuminate _some_ path or intent - is that not helpful? Is it _always_ better to rely on just the code - even when it requires copious amounts of mental overhead to understand?


## Explain Yourself in Code
- Code can make a poor vehicle for explanation.
  - Agreed, and I think that's my argument for the relevance of comments in the right context.
  - The example given resonates with me (checking several statements in-line inside of a conditional vs. obj.checkConditions())
    - I see the former a lot. I did the former a lot.
    - I think I did this a lot because it felt like the latter was an unneccessary abstraction...till you go back to that code six months later and need to remind yourself what all of those in-line conditions are again.


