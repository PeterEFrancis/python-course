# `random`

"Random" numbers are important for code testing, games, and much more. Here, we will discuss python's `random` module, which gives us psuedo-random choice capabilities.


### Import the `random` module

```python
import random
```

### Get a random `float` *exclusively* between 0 and 1

```python
random.random()
```
> `0.549675920428354`

(You will get a different number.) This random number is chosen with a uniform distribution.

### Get a random integer between two *inclusive* bounds

```python
upper = 15
lower = 3
random.randint(lower, upper)
```
> `15`

(You will get a different number.)

### Set the seed

A seed can be any [hashable](https://docs.python.org/2/glossary.html#term-hashable) type (numbers, strings, for example). The seed determines the state of the random number generator, so determines the actions after it is set. That is, the seed allows for reproducible random numbers. If you run the following, you should see exactly the same output:

```python
random.seed(100)
for _ in range(5):
	print(random.random())
```
> 0.1456692551041303
>
> 0.45492700451402135
>
> 0.7707838056590222
>
> 0.705513226934028
>
> 0.7319589730332557

To clear the current seed, call `random.seed()` (with no argument).



More information: https://www.w3schools.com/python/module_random.asp
