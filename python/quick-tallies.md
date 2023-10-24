# Quick talies

You should use Counter when you need to quickly count how many times something appears, whether in a string or in an array. Surprising amount of utility for something that just counts occurrences.

```py
words = re.findall(r'\w+', open('hamlet.txt').read().lower())
Counter(words).most_common(10)
```

[source](https://docs.python.org/3/library/collections.html#counter-objects) (The real source is probably Norvig's Pytudes)
