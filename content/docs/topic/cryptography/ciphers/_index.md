# Cryptographic Ciphers

## Caesar Ciphers

One of the first ciphers, with the first recorded use by Julius Caesar between 100-44 BC

### Methodology

Replaces each plaintext letter with the letter a fixed number of places down the alphabet.

Encryption

<img src="https://latex.codecogs.com/svg.latex?c_i:=(p_i+k)mod26">

Decryption

<img src="https://latex.codecogs.com/svg.latex?p_i:=(c_i-k)mod26">

### Vulnerabilities and Attacks

**Brute Force**

As there are only 26 possible keys, we could try all of them until one of them works.

**Cryptanalysis**

Frequency Analyses: English text has distinctive letter frequency distribution

## Vigenere Ciphers

First described by Bellaso in 1553, later misattributed to Vigenere. Called 'le chiffre indechiffrable' ('the indecipherable cipher').

Encrypts successive letters using a sequence of Caesar ciphers determined by the letters of a keyword.

For an n-letter keyword k,

Encryption

<img src="https://latex.codecogs.com/svg.latex?c_i:=(p_i+k_{imodn})mod26">

Decryption

<img src="https://latex.codecogs.com/svg.latex?p_i:=(c_i-k_{imodn})mod26">

### Vulnerabilities and Attacks

**Cryptanalysis**

Frequency Analyses

## One-Time Pad