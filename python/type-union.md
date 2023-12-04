# Type unions for input

Type unions are basically super "types" that can be one of anything. The neat part of this is when you're parsing input, you can use these super types to return the correct type for whatever you're parsing

```py
Atom = Union[str, int, float]

def atom(text: str) -> Atom:
    try:
        x = float(atom)
        return round(x) if x.is_integer() else return x
    except ValueError:
        return text.strip()
```