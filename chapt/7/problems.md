
1. Call a generator which takes in no arguments and yields successively all the terms in an infinite sequence a *sequence generator*. For example, here is a sequence generator which yields the terms in the sequence $1, 2, ..., n, ...$:

```python
def count():
	curr = 1
	while True:
		yield curr
		curr += 1
```

To use this sequence generator, we might, for example, iterate infinitely as so:

```python
for num in count():
	print(num)
```

Or, we might take the first few elements using the `next` function:

```python
c = count()
a1 = next(c)
a2 = next(c)
assert(a1 == 1 and a2 == 2)
```

a. Write a generator which takes as an argument a sequence generator, and yields the sequence given by doubling every element of the original sequence.
b. Write a generator which takes as an argument two sequence generators, and yields the sequence given by interleaving them. That is, if $A$ is a sequence generator that yields $a_1, a_2, ...$, and $B$ is a generator that yields $b_1, b_2, ...$, the interleaving of $A$ and $B$ yields $a_1, b_1, a_2, b_2, ...$. (Note: the interleaving of sequences is also known as `zip`, and there's a builtin function `zip` to do that, but don't use it here!)
c. Write a function which takes as arguments two sequence generators, and returns whether their first 10 elements are the equal.
d. Write a function that approximates the limit of the sequence yielded by a sequence generator.
