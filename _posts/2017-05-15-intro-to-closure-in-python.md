---
layout: post
title: "Introduction to closures in python"
---

Closures are one of the widely misunderstood programming concept around. While it may seem like they are a bit on advanced spectrum of programming concepts, but in reality they are really simple. Once you understand the basic of what really a so called closure is, then it's easy from there.
So, let's dive right into it.

I will go through a simple example to get started.
Let's say you are solving a problem which requires you to raise a number to a certain exponent. Now in python the obvious way to do this is using it's own `pow()` builtin function. Let's say we really do not want several `pow()` in our code. We want our solution to be more pythonic. 
We go ahead and create a function for that.
```python
def power(x, n):
    return pow(x, n)
```
Well that does the job, for now. Let's say our code requires a lot of number which are raised to certain exponents a number of times, specifically let's consider a number being raised to power of 2, 3 and 10. Now the above function will also serve our purpose, but it does feel like we are performing some tasks repeatedly.
Let's say we want to raise two integers `x` and `y` to the powers of 2, we'll have to call the above function twice like shown below.
```python
power(x, 2)
power(y, 2)
```
This will get ugly real fast, hadcoding our function calls with numbers doesn't seem right.
Now, here comes our oppurtunity to use closures. Let me show the code first for one implementation.
```python
def power(exponent):
    return lambda x: x * exponent
```
Now hold on for a bit, the above code is just another function definition. Here `power()` is a function which takes an exponent as it's argument and returns something called a lambda function. Well focusing on it's return value is nothing but like a normal function, wherein it takes an argument x and multipleis it with the parent functions argument exponent.
So essentially, the above power function is returning to us a a new function definition which makes use of our passed in exponent value.
Now, the benefit of the above is that we can define new function
