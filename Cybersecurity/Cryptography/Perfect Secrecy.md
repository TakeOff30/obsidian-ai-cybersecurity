**Perfect secrecy** is a property of certain encryption systems that ensures the ciphertext provides no information about the plaintext, even to an attacker with unlimited computational resources. This concept was formally defined by Claude Shannon in his groundbreaking work on information theory.
#### Definition
An encryption scheme has **perfect secrecy** if, for every possible plaintext PP and every possible ciphertext CC, the conditional probability of the plaintext given the ciphertext is equal to the probability of the plaintext:

$P(P = p \mid C = c) = P(P = p)$

- The ciphertext $C$ does not change the probability distribution of the plaintext $P$.

In other words, knowing the ciphertext $C$ does not change the probability distribution of the plaintext $P$.
#### Implications

1. **No Information Leakage**: The ciphertext reveals absolutely no information about the plaintext.
2. **Unbreakable**: Even with infinite computational power, an attacker cannot deduce the plaintext from the ciphertext.
3. **Key Requirements**: To achieve perfect secrecy, the key must:
    - Be **truly random**.
    - Be **as long as the plaintext**.
    - Be **used only once** (as in the [[One-Time Pad]]).
        
#### Limitations of Perfect Secrecy

While perfect secrecy is a strong theoretical guarantee, it is difficult to achieve in practice due to:
1. **Key Distribution**: Securely sharing a key as long as the message is challenging.
2. **Key Management**: Generating and storing truly random keys of sufficient length is impractical for large-scale use.
3. **Reusability**: Keys cannot be reused without compromising security.
