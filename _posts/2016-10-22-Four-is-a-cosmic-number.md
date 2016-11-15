---
layout: post
title: Four is a cosmic number
category: Data Science
tags: [Python, matplotlib]
---

Quick plot of a VSauce video example, using matplotlib and Python

## Four is a cosmic number

Hey everyone,

I am sure some of you like VSauce on YouTube, he made a [video](https://youtu.be/csInNn6pfT4) 3 weeks ago on fixed points. At 13:00 he talks about why 4 is considered a cosmic number and he had this funny experiment:




1. name any number in English
2. count the number of letters in its name: this gives you a new number
3. go back to the second step and repeat

Every single time you will end up at 4 where you will be stuck in an infinite loop.

I thought it would be funny to code it and plot the behavior of the function, so, I coded a recursive function that does exactly what is described on the steps above and then I plotted the result of step 2 at each iteration.

Here is the code:

```python
from num2words import num2words
import matplotlib.pyplot as plt

def letter_pyramid(number):
	if(number == 4):
		return [4]
	else:
		length_spelled_number = len(num2words(number))
		return [length_spelled_number] + letter_pyramid(length_spelled_number)


for n in range(0, 100, 1):
	l = [n] + letter_pyramid(n)
	plt.plot(l)

plt.xlabel("n iteration")
plt.ylabel("numerical value")

plt.show()
```

Here is the graph for all the integers in [0, 1, 2, 3... , 99, 100].

![alt text](https://media.licdn.com/mpr/mpr/shrinknp_800_800/AAEAAQAAAAAAAAd1AAAAJGQxNTEyNmQ0LWYyYWMtNGI4Ni04MzFkLTRjNjU3Y2UyYjk0MQ.png "Plot for x in [0, 1, 2,... 100]")

As you can see, the values all converge to 4 eventually :)

Thank you for reading :)

### Here is the original video
<a href="http://www.youtube.com/watch?feature=player_embedded&v=csInNn6pfT4" target="_blank"><img src="http://img.youtube.com/vi/csInNn6pfT4/0.jpg" alt="Fixed points" width="240" height="180" border="10" /></a>