
Cryptographic attacks are methods used to break or weaken cryptographic systems. The type of attack depends on the information available to the attacker.
#### 1. [[Brute-Force Attack]]
- **Definition**: Trying every possible key.
- **Countermeasures**: Use longer keys, implement rate-limiting.
#### 2. [[Ciphertext-Only Attack]]
- **Definition**: Attacker has only ciphertext.
- **Countermeasures**: Use strong encryption, ensure keys are random.
#### 3. [[Known Plaintext Attack]]
- **Definition**: Attacker has plaintext-ciphertext pairs.
- **Countermeasures**: Use modern algorithms, avoid key reuse.
#### 4. [[Chosen Plaintext Attack]]
- **Definition**: Attacker can choose plaintexts and get ciphertexts.
- **Countermeasures**: Use secure encryption modes, implement key randomization.
#### 5. [[Chosen Ciphertext Attack]]
- **Definition**: Attacker can choose ciphertexts and get plaintexts.
- **Countermeasures**: Use authenticated encryption, implement padding schemes.