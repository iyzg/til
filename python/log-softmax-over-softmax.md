# You should use Log Softmax

I've always known that you could use Softmax to change a Tensor to probabilities of each class occuring, but I only just realized *why* you would want to use Log(Softmax) instead of just Softmax.

As the first source talks about, numerical stability is **important.** When you're trying to do optimizations, overflows and nans are what will kill runs. In light of this, it makes sense to use a log scale since that will ensure that it is impossible to get nans. The approach of doing $\frac{e^x_i-max(x)}{\sum_je^x_j-max(x)}$ is a bit more prone to underflows, but this is preferable than having any overflows.

It also seems to require less numerical computations which is quicker than just doing softmax. Really, it seems like there's not much reason to *use* Softmax, as you can always take $e^log_softmax(x)$ if you want to retrieve the softmax for some reason. For `Negative Log Likelihood Loss (NLLLoss)`, the function also expects a log softmax, so yet another reason in case that wasn't enough!

[source](https://jaykmody.com/blog/stable-softmax/)
[source](https://pytorch.org/docs/stable/generated/torch.nn.LogSoftmax.html)