# Create masks from arrays

```py
a = np.array([[0, 1, 2], [3, 4, 5]])
>>> a
array([[0, 1, 2],
       [3, 4, 5]])
>>> a > 3
array([[False, False, False],
       [False,  True,  True]])
>>> a[a > 3]
array([4, 5])
>>> 1 * (a > 3)
array([[0, 0, 0],
       [0, 1, 1]])
```

If you want to make a mask out of an array, you can simply do, `MASK_COND` or `1 * (MASK_COND)` if you're trying to create an int array.

To extract the elements which meet the requirements, you can do `a[MASK_COND]`.
