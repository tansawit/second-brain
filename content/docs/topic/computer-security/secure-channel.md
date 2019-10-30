---
bookToC: 2
---

# Secure Channel

A secure channel is a way of transferring data that is resistant to overhearing and tampering

A secure channel has the following properties:

## Confidentiality

Confidentiality means that contents of a message is kept secret from any eavesdropper.

Nomenclature:

<img src="https://latex.codecogs.com/svg.latex?p"> = plaintext

<img src="https://latex.codecogs.com/svg.latex?c"> = ciphertext

<img src="https://latex.codecogs.com/svg.latex?k"> = secret key

<img src="https://latex.codecogs.com/svg.latex?E"> = encryption function

<img src="https://latex.codecogs.com/svg.latex?D"> = decryption function

### Techniques

- [Caesar Ciphers]({{<relref "docs/topic/../../../cryptography/ciphers/#caesar-ciphers">}})
- [Vigenere Ciphers]({{<relref "docs/topic/../../../cryptography/ciphers/#vigenere-ciphers">}})
- [One-time Pads]({{<relref "docs/topic/../../../cryptography/ciphers/#one-time-pad">}})

## Integrity

Message integrity means that an attacker cannot modify messages without being detected.

For example, is Alice is sending a message to Bob, we want to ensure that Bob receives what Alice actually wants to send

### Threat Model

Mallory, the attacker, can see, modify, and forge messages (i.e. Man-in-the-Middle Attacks)

Mallory wants to trick Bob into accepting a message Alice didn't send

### Defense

Alice computes <img src="https://latex.codecogs.com/svg.latex?v:=f(m)">

For example, message m = "Attack at dawn", f(m) = 7489890283840

Bob verifies that <img src="https://latex.codecogs.com/svg.latex?v'=f(m')">, and accepts the message if and only if this is true.

We want <img src="https://latex.codecogs.com/svg.latex?f"> to be easily computable by Alice and Bob, but not easily computable by mallory

We lose if Mallory can learn <img src="https://latex.codecogs.com/svg.latex?f(x)"> for any <img src="https://latex.codecogs.com/svg.latex?x\ne m">

#### Random Functions

Input: Fixed size (message size)

Output: Fixed size (e.g. 256 bits)

Secure, but impractical

##### Pseudo-random Functions (PRF)

A function that 'looks random', but remains practical.

**Building a PRF**

Kerchoff's Principle: A cryptosystem should be secure even if everything about the system, except the key, is public knowledge.

Start with a big family of functions <img src="https://latex.codecogs.com/svg.latex?f_0(),f_1(),f_2()">... all known to Mallory

<img src="https://latex.codecogs.com/svg.latex?f_i:\{0,1\}^n\rightarrow\{0,1\}^n">

Let <img src="https://latex.codecogs.com/svg.latex?g">, our verifier function, be <img src="https://latex.codecogs.com/svg.latex?f_k()"> where <img src="https://latex.codecogs.com/svg.latex?k"> is a secret index/key only known to Alice and Bob.

<img src="https://latex.codecogs.com/svg.latex?k"> is <img src="https://latex.codecogs.com/svg.latex?n"> bits, chosen randomly.

**Formal Definition of a PRF**

1. Flip a coin secretly to get bit <img src="https://latex.codecogs.com/svg.latex?b">
2. If <img src="https://latex.codecogs.com/svg.latex?b=0">, let <img src="https://latex.codecogs.com/svg.latex?g"> be a random function. If <img src="https://latex.codecogs.com/svg.latex?b=1">, let <img src="https://latex.codecogs.com/svg.latex?g=f_k">, where <img src="https://latex.codecogs.com/svg.latex?k"> is a randomly chosen secret
3. Mallory chooses <img src="https://latex.codecogs.com/svg.latex?x">: we announce <img src="https://latex.codecogs.com/svg.latex?g(x)">. Repeat as often as Mallory likes
4. Mallory guesses <img src="https://latex.codecogs.com/svg.latex?b"> quickly

Definition: We say that <img src="https://latex.codecogs.com/svg.latex?g()"> is a secure PRF if Mallory can't select <img src="https://latex.codecogs.com/svg.latex?b"> any better than random guessing.

Note: We do not know if a true pseudo-random function exists. Currently mostly using functions where we haven't spotted a problem yet (e.g. HMAC-SHA256)

##### Pseudo-random Generators (PRG)

Takes small seed that is really random

Generates a sequence of number that is "as good as random"

A PRG is secure if it's indistinguishable from random

1. We flip a coin to get a bit <img src="https://latex.codecogs.com/svg.latex?b">
2. if <img src="https://latex.codecogs.com/svg.latex?b=0">, let <img src="https://latex.codecogs.com/svg.latex?s"> be a truly random stream
3. if <img src="https://latex.codecogs.com/svg.latex?b=1"> late <img src="https://latex.codecogs.com/svg.latex?s"> be <img src="https://latex.codecogs.com/svg.latex?g_k"> for a random secret <img src="https://latex.codecogs.com/svg.latex?k">
4. Mallory can see as much of the output of <img src="https://latex.codecogs.com/svg.latex?s"> as they want
5. Mallory wins if guesses <img src="https://latex.codecogs.com/svg.latex?b"> correctly

We consider <img src="https://latex.codecogs.com/svg.latex?g"> to be a secure PRG if there is no winning strategy for Mallory

#### True Randomness

Where do we get true randomness?

Modern OSes typically collect randomness, provide API to get it. For example, on Linux, /dev/random is a device that gives random bits and blocks.

## Authenticity