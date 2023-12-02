# For-elses

If you ever want to use a for loop to check for a condition or look for some value, you'll want to break out of it once you've got what you're looking for. Instead of using a flag to handle the case where you don't break, you can instead attach an else to your for loop.

```py
for factor in range(2, num):
    if num % factor == 0:
        break
else:
    print('Found a prime')
```