# Finding the Top-K

Pulling the Top-K is useful when you want to sample from a LLM, pull from a distribution, or simply get the Top/Bottom-K items in an array. (Code and then explanation below)

```py
res = np.partition(ar, -k)[-k:]
res = np.sort(res)
```

Version to get indices (useful for when you need to pull values out of multiple arrays at once):

```py
ind = np.argpartition(ar, -k)[-k:]
ind = ind[np.argsort(ar[ind])][::-1]

res = [ar[i] for i in ind]
```

`np.partition` takes an array and an index, and it will ensure that the `kth` element is correctly sorted, all smaller elements are before, and all larger are above. (You can think of this like a [quicksort partition](https://en.wikipedia.org/wiki/Quicksort#:~:text=Quicksort%20is%20an%20efficient%2C%20general,commonly%20used%20algorithm%20for%20sorting.) if it helps!)

> NOTE: Partitioning does **NOT** guarantee the partitioned areas will be sorted. Just that the element you select is in the right place.

Like all numpy commands prefixed with args, all `argpartition` does is the same thing, but returns an array of indices rather than the values of the array. By then doing `[-k:]`, we're pulling the guaranteed indices of the top-k elements and storing them in `ind`. (We also pass `-k` in for the partitioning since we want the largest k values, it would be `k` for smallest)

Now let's break down `ind = ind[np.argsort(ar[ind])][::-1]` from the inside out. `ar[ind]` pulls out the top-k values using the indices we just got and pass them into `np.argsort()`. `sort` just sorts the elements, and using the same `arg` design pattern as before, `argsort` sorts the elements but returns a list of sorted indices rather than the elements.

An example of argsort:
```py
>>> x = np.array([3, 1, 2])
>>> np.argsort(x)
array([1, 2, 0])
```

`np.argsort(ar[ind])` holds the order of how to sort `ind` so that the corresponding values in `ar` will be sorted, and `ind[np.argsort(ar[ind])]` sorts our index array, so as we step through the `ind` array, the values in `ar` only get larger. The slice of `[::-1]` means we go through all our elements, but step *backwards* rather than forwards. This reverses our sorted index list to go in descending order. We now have the indices of the Top-K elements in reverse order (largest to smallest).

Finally, we can iterate through the indices of the Top-K elements and add them to a list with `[ar[i] for i in ind]`.

[source](https://github.com/lilianweng/emoji-semantic-search/blob/main/server/app.py) [so](https://stackoverflow.com/questions/52465066/how-does-numpys-argpartition-work-on-the-documentations-example)