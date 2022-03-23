---
title: Back to Basics - Clean Code Chapter Three 
date: 2022-03-11T22:20:14.670Z 
description: Revisiting good practices reading Clean Code by Robert Martin
---

Continuing my journey back into Uncle Bob's _Clean Code_ I've completed chapter three on functions. There is a lot of gold in the points covered here. I found the use of before and after code examples with refactors to be extremely helpful to really draw the distinction between good and bad implementation. Also, in that regard, I really appreciate being given a real world code example as part of the text. One of my biggest issues with these types of technical books is that often times the examples are simple by design to only convey a concept; that is sometimes useful but I also find it difficult to then find practical examples I would apply that concept to. Overall I learned quite a bit and so I'm just going to jump into my notes.

### The Rules:
- The first rule is that _functions should be small_
  - This is such an easy thing to over look. Seriously - it is _very_ easy to write something that accomplishes your goal that is verbose and simply say "well, I don't think this can be broken down so...moving on".
  - Keeping the goal of _small_ functions top of mind can force you to parse out your task a bit different ahead of time.
  - He mentions at the end of the chapter that he often just writes a mess to get something working then applies this concepts after - but I'd argue that keeping a goal of small functions from the start helps inform your approach even if your writing a big ol monolith to start.
- Measurements - he gives some concrete lengths to not surpass
  - should not be over 150 chars long
  - should not be 100 lines long
  - should hardly ever be 20 lines long
- I think the last bullet is the one to really consider. If you're surpassing 20 lines you've probably got at least one opportunity to split things out if not more. If you don't you need to consider what is preventing you from doing so as there is probably a larger issue at play.
- As an aside; I always kind of thought that splitting things out into smaller functions just contributed to overhead required to understand how something worked. If I'm having to continually bounce from a public method down to a handful of private methods that do smaller things - that's just confusing. But when you couple smaller functions with the naming rules covered in chapter two things start to be more explicit and you should only be dipping into those private methods if they're not behaving correctly.
- Indents
  - blocks with `if`, `else`, and `while` statements should be one line long.
  - really, our functions should only be one indentation level deep
  - your functions _should not be large enough to hold nested structures_
  - any more probably signals that you have a potential function call


### Do One Thing:
I've always tried to follow this as a very basic principle. But, honestly - oftentimes it's really hard to draw the line one what _one_ thing you are accomplishing with your function. If you are parsing a string in a function and searching for a given value and returning true if found; is that two distinct things? Even if the parsing and searching can be chained together or they're very short snippets of code in-and-of themselves? We're given some direction on how to deduce if we're doing _more_ than one thing in this subsection.

- FUNCTIONS SHOULD DO ONE THING. THEY SHOULD DO IT WELL. THEY SHOULD DO IT ONLY. - I want a giant print out of this for my wall as a constant reminder.
- Using _TO_ paragraphs
  - Here's the direction on sorting out if you're doing too much. Use the format `TO [function name]...` and follow with plain english implementation.
    - If the function does only the steps one level below the given function name then the function is doing one thing.
      - So, for instance, the string parsing example. If we called the function `searchParsedStringForTerm` we could sort out that it is doing one thing by writing out `TO searchParsedStringForTerm we parse the string by spaces into an array and search that array for the given term. If we find the given term we return true else we return false`.
      - I think an appropriate example of doing more than one thing in the string parsing example would be if we were also seeing if the term that is found is inside of some other data structure. In that instance we'd have to add another condition after searching the parsed string to check if the other data structure included that value. At that point you probably have one function for parsing and searching and one for checking if that value is in the other structure.
  - Another approach is - if you can extract another function from your current function without merely restating it's implementation - you probably are doing more than one thing.

