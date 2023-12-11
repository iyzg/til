# Common zip design patterns

Even though the documentation already mentions this way of thinking, it had never occurred to me that you can use `zip` as ["transposing"](https://en.wikipedia.org/wiki/Transpose) your list.

```py
for name in zip(['Alice', 'Bob', 'John'], ['Smith', 'Poe', 'Doe'])
    print(name)

# > ('Alice', 'Smith')
# > ('Bob', 'Poe')
# > ('John', 'Doe')
```

So in the above example, you're taking the 2x3 matrix and making it 3x2.

You can also use it to quickly replace for loops with indexing and then accessing multiple elements

```py
first_names = ['Alice', 'Bob', 'John']
last_names  = ['Smith', 'Poe', 'Doe']

for first, last in zip(first_names, last_names):
    print(first, last)

# > ('Alice', 'Smith')
# > ('Bob', 'Poe')
# > ('John', 'Doe')
```



