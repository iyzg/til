# Class properties are neat

```py
def __init__(self):
    self._messages = None

@property
def messages(self):
    if self._messages is None:
        self._load_msg_embeddings()
    return self._messages
```

Neat little design pattern on how you can have private variables then public access through `class.variable`, except the "variable" they're pulling is a function, so you can do other operations before the final return.

[source](https://github.com/lilianweng/emoji-semantic-search/blob/main/server/data/build.py)