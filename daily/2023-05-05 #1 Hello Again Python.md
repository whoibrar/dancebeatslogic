---
date : "2023-05-05"
title : "#1 Hello Again Python"
slug : "1-hello"
time : "3h-00m"
summary : "I started learning Data Science on DataCamp"
---

I Started with [Introduction to Python](https://app.datacamp.com/learn/courses/intro-to-python-for-data-science) course on DataCamp, as I did need a refresher. It has some 4 sub-modules, and shows it’s 56% done or 2 more hours to go. This intro course itself is just 4 hours. This course is part of the longer career track that I want to finish, titled [Data Scientist with Python](https://app.datacamp.com/learn/career-tracks/data-scientist-with-python), which is just a collection of other learning material, 23 courses, 6 projects and 3 assessments to be precise. It shows 90 Hours of learning, hopefully should be able to finish soon. 

I hoped I’ll be able to finish it the intro course today, given that I spent 3hrs in total but in my defense there are too many call to action buttons for different tracks and courses on website, took me a while to choose what I should focus on.

Lessons starts with a video explanation of the topic then followed by a simple exercise which is split screen interface, with instructions on left and code editor, shell on right. Both the learning and testing happens at the same stage, I really like this approach, which is also followed by [FreeCodeCamp](https://www.freecodecamp.org/). 

This does sound like [Astroturfing](https://en.wikipedia.org/wiki/Astroturfing) from DataCamp, but it’s not. The main reason why I chose it is because of I had gotten 3 months free with GitHub student developer pack also because it had projects, but mostly because I got it for free.

And it’s not all sunshine though on two occasions the video wouldn’t play at all. Had to make sense of the lesson using transcript and slides. I did reported it. 

Otherwise it was a seamless experience also kind of nostalgic, since it had been more than year since I switched to C++. I wrote the first *“Hello World”* in python some 3 years back, a few weeks before covid became a thing, learning it from the book [automate the boring stuff with python](https://automatetheboringstuff.com/). At the time I wasn’t aiming to learn to code but to make my life easier by letting go mundane tasks like renaming and organizing files. This book seem to promise just that. And Oh boy, did it deliver. Highly recommend it.

I was so accustomed to C++ static type syntax, I accidently declared a variable using `int a`. I quickly realized the mistake but an interesting question popped up. 

*Since python is dynamically typed and we initialize a variable at the time of declaration, **Is it even possible to declare a variable without initializing it in python ?*** Surprisingly the answer is ~ drum rolls ~ Yes! and there are actually two ways of doing it.

```python
# Assinging the value of None
a = None
print(a) #None
print(type(a)) #<class 'NoneType'>

# Using the ... aka ellipsis
b = ...
print(b) #Ellipsis
print(type(b)) #<class 'ellipsis'>

```

Also learned that variables doesn’t actually exist. It’s all just Names. What’s the difference you ask ? Well, it’s a story for another time. [Link for the impatient](http://web.archive.org/web/20180331085022/http://python.net/~goodger/projects/pycon/2007/idiomatic/handout.html#other-languages-have-variables).
