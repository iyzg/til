# GANs train discriminators first

The basic training loop for a GAN is something like:

```py
for e in range(epochs):
    for k in range(steps):
        train_discriminator()
    train_generator()
```

There are smarter training loops where you choose which to train based off loss and gradient norms, but the general principle is the same. You want to get the discriminator to make a bit of progress *first* so the generator has some sort of signal to follow. Pleasantly surprised by how simple it is to code up a GAN.
