# Addition for skip connections

```py
def _backward():
    self.grad += 1.0 * out.grad
    other.grad += 1.0 * out.grad
```

When neural networks use skip connections (connections from early layers to later ones), they usually use addition. This is since the partial derivative of any addition will be 1.0, so you can think of this as carrying gradients directly to the beginning parts of a network. 

It's a bit interesting how understanding gradients directly leads to intuition of how to structure a network!