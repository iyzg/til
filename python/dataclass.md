# Dataclasses as little storage containers

A common design pattern is having classes that simply hold state which you pass around to manipulate & keep track of how a program is running or instances of an object.

For doing something like that in Python, you can use:

```py
from dataclasses import dataclass

@dataclass
class Book:
    name: str
    author: str
    year: int = 0
```

The dataclass decorator will automatically add `__init__()` and `__repr()__`, so although not completely necessary, it's a nice little syntactic sugar to clean up any classes you have which mostly store state.
