---
title: "Generative Adversarial Networks Course (Google)"
bookHidden: true
---

# Google's Generative Advesarial Networks Course

## Generative Models

"Generative" describes a class of statistical models. Compared to discriminative models:

- **Generative** models can generate new data instaces
- **Discriminative** models discriminate between different kinds of data instances

Formally:

- Generative models capture the joint probability <img src="https://latex.codecogs.com/svg.latex?p(X,Y)">, or just <img src="https://latex.codecogs.com/svg.latex?p(X)"> if there are no labels
- Discriminative models captures the conditional probability <img src="https://latex.codecogs.com/svg.latex?p(Y|X)">

A generative model includes the distribution of the data itself, and tells you how likely a given example is. Conversely, a discriminative models ignores the question of  whether a given instance is likely, and just tells you how likley a label is to apply to the instance

### Modeling Probabilities

Neither mels has to return a number representing a probability. You can model the distribution of data by imitating that distribution. A generative model can model a distribution by producing convincing "fake" data that looks like it's drawn from th distribution.

## GAN Structure

Both the generator and discriminator are neural networks, with the generator output directly connected to the discriminator input. Through backpropagation, the discriminator's classification provides a signal that the generator uses to update its weights.

### Generator

The **generator** learns to generate plausible data. That data bcomes the negative training examples for the discriminator

Its training requires tighter integration between the two parts than the discriminator training.

Portions of GAN that trains the generator:

- random input (e.g. noise) 
- generator network (transforms random input into data instance)
- discriminator network (classifies the generated data)
- discriminator output
- generator loss (penalizes the generator for failing to fool the discriminator)

Using the Discriminator to Train the Generator

Alter the net's weights to reduce the loss of its output. The generator is not directly connected to the loss that we're trying to affect. The generator feeds into the discriminator net, and the discriminator produces the output we're trying to affect. The generator loss penalizes the generator for producing a sample that the discriminator network classifies as fake.

The impact of a generator weight depends on the impact of the discriminator weights it feeds into. So backpropagation starts at the output and flows back through the discriminator into the generator.

Training Procedure (1 iteration):

- Sample random noise
- Produce generator output from sampled random noise
- Get discriminator to classify for the output
- Calculate loss from discrimminator classification
- Backpropagation through the discriminator and generator to obtain gradients
- Use grad#nts to change only the generator weights

### Discriminator

The **discriminator** learns to distinguish the generated data from the real ones. It the penal?es the generator for producing implausible results.

Source of training data:

- Real Data (real pictures of people). Positive examples 
- Generated Data (pictures created by generator). Negative examples


Training:

The discriminator connects to two loss functions. During tr ning, it ignores the generator loss and only uses the discriminator loss.

Procedure:

- Discriminator classifies both real and fake data from the generator
- Discriminator loss penalizes the it for misclassification
- Discriminator updates its weight through backpropagation
