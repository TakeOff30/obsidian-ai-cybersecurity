
**Kerckhoffs's Principle** states that the security of a cryptographic system should depend solely on the secrecy of the key, not on the secrecy of the algorithm.

#### Origin
- Proposed by **Auguste Kerckhoffs** in 1883.
- Published in *"La Cryptographie Militaire"*.

#### The Principle
> "The system must not require secrecy and can be stolen by the enemy without causing trouble."

1. The algorithm should be public.
2. Security relies entirely on the key.

#### Why It Matters
1. **Transparency**: Public algorithms can be scrutinized.
2. **Security Through Obscurity is Flawed**: Hiding the algorithm is risky.
3. **Easier Key Management**: Focus on securing keys.

#### Modern Interpretation
- Applied in [[Symmetric Encryption]] (e.g., [[AES]]) and [[Asymmetric Encryption]] (e.g., [[RSA]]).
#### Applications
1. **Public Cryptography Standards** (e.g., AES, RSA).
2. **Open-Source Cryptography**.
3. **Key Management Systems**.