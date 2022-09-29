---
layout: post
title:  "Comprehending Python: A Guide to List and Dictionary Comprehensions"
date:   2022-09-28
author: Rachel Miles
description: The different kinds of list comprehensions and dictionary comprehensions you can use to bypass for loops can be a little complicated, and I literally love doing anything that doesn't involve for loops, so lets see if we can't figure it out!
image: /assets/images/kevin-ku-w7ZyuGYNpRQ-unsplash.jpg
---

Any student who has learned the coding language for R and Rstudio has heard: Do not use loops! They're not worth it! As a dutiful student who was blissfully unaware of how other programming language worked, I took this direction quite literally. Any time I didn't have to use a for loop was a success. Unfortunately after becoming familiar with C++, SAS, python, and Linux, I realized that this approach was not sustainable. These different languages thrive on using for loops to generate and populate objects. Without a for loop, you really can't do much coding at all. The coding it would take to add things by hand isn't worth it, trust me, so I resigned myself to learn for loops.

Once learning python however, I realized that there are alternatives to using loops. I'm specifically referring to list and dictionary comprehensions. List and dictionary comprehensions work similarly to for loops, just in a different form. They also save the step of intialize and empty list or dictionary, which is always a plus. Anything to write less code, am I right? 

## List Comprehensions
As I said before, list comprehensions are essentially for loops in a different form with the built in step of intializing a list. Here is a sample for loop to create a list of numbers ranging from 1 to 50 which are divisible by 4. X is an arbitrary variable I came up with, it has no special value before this line of code. 

``` {code}
list = []
for x in range(1, 50):
    if x % 4 == 0:
            list.append(x)
print(list) 
```

Here is the code for a list comprehension that preforms the same function. X is still an arbitrary variable. Notice how there is still a for statement and an if statement. It's essentially the same thing smashed into one line. 
``` {code}
list = [x for x in range(1, 50) if x % 4 == 0]
print(list)
```
##### Lets break it down. 
Start from the left. We make a list (in this case named list) equal to the list comprehension of the arbitrary variable X for X in a group of number ranging from 1 to 50 that are divisible by 4. There's almost no difference between the for loop above and this list comprehension except for the fact that it's on one line, the words are in brackets, there's no colons, and there's an extra use of X at the beginning.

I would also like to note that it helps to make a for loop for every list comprehension you make, at least at the start. It may seem like it defeats the purpose of coding the list comprehension, but it does help to build it since they both have the same building blocks. Eventually you should be able to write list comprehensions without doing that step, but if you're having trouble, it's a good middle step to try. 


## Dictionary Comprehensions
Dictionary Comprehensions work very similarly to list comprehensions in that you are using the building blocks of a for loop in one line while simultaneously intializing a dictionary. For the sake of being concise, I will not include a for loop version of this, but instead simply show the code for the dictionary comprehension and how it uses for loop building blocks. 

This code is essential making the same list as both the for loop and the list comprehension, as in creating a group of numbers ranging from 1 to 50 which are divisible by 4. The key to each number is that number divided by 4, which makes the keys end up being a count from 1 to the end of the list. 

Note that the variable used here is referred to as key, but once again is a completely arbitrary choice. 

Here is that code:
``` {code}
dictionary = {key: [key/4] for key in range(1, 50) if key % 4 == 0}
print(dictionary)
```
##### Let's break it down
We make a dictionary (in this case named dictionary) equal to the dictionary comprehension of the arbitrary variable key where the value is the key divided by 4. I like the look of having each key and corresponding value on different lines and in brackets, so that's what the brackets around key/4 is, but that isn't required. The range is from 1 to 50 and the key must be divisible by 4. 

Once again, notice the use of a arbitrary variable in a for statement within a set range and an if condition. The only change is the automatic intialization of the dictionary and how I denoted what I wanted the key to be.

## Conclusion
Making dictionaries and lists can be hard. For loops can make this process easier, but there are built in functions (list comprehensions and dictionary comprehensions) which are designed to make this process easier and more efficient. It helps to make the for loops along side the comprehensions when starting out to learn the building blocks that go into making list and dictionary comprehensions. They may seems different at first, but there are essentially the same code written differently.

Happy coding!

