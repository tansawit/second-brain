# Hashing

## Hash Functions

Input: Arbitrary-Length Data

Output: Fixed-size digest (n bits)

Properties

- No keys
- Fixed Function

Examples: SHA-256, SHA-512, SHA-3

### Characteristics of a Good Hash Function

Collision Resistance

- Hard to find pair of input x, x′ such that H(x) = H(x’)

Preimage Resistance

- Given y, hard to find x′ such that H(x′) = y

Second Preimage Resistance

- Given x, hard to find an x′ such that H(x) = H(x′)

### SHA-256

#### Basics

Input: Arbitrary Length Data

Output: 256-bit digest 

Built with “compression function” h using Merkle–Damgård construction

<img src="https://latex.codecogs.com/svg.latex?h:(256bits,512bits)\rightarrow256bits"> out

#### Algorithm

1. Pad input <img src="https://latex.codecogs.com/svg.latex?m"> into multiple of 512 bits using a fixed algorithm
2. Split into 512-bit blocks <img src="https://latex.codecogs.com/svg.latex?b_0,b_1,...b_{n-1}">
3. <img src="https://latex.codecogs.com/svg.latex?y_0"> = constant initialization vector, <img src="https://latex.codecogs.com/svg.latex?y_1=h(y_0,b_0)...,y_i=h(y_{i-1},b_{i-1})">
4. Return <img src="https://latex.codecogs.com/svg.latex?y_n">


### Other Hash Functions

MD5

- Once ubiquitous
- Broken in 2004
- Now easy to find collisions


SHA-1

- Fairly widely used
- Started to be unsupported in HTTPS in January 2016