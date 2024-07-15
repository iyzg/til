## Vose-Alias Method

I remember reading that [Node2Vec](https://arxiv.org/abs/1607.00653) used something called the "alias method" to sample from a discrete distribution in O(1), and I've finally tracked it down. By simulating a fair dice toss and then a biased coin, you're able to sample from discrete distributions instantly with just a bit of precomputation!

[src](https://www.keithschwarz.com/darts-dice-coins/) [src](https://y7k4.github.io/2021/03/23/alias-method.html)