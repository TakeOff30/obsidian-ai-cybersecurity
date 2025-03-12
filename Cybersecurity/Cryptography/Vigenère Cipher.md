The **Vigenère Cipher** is a **polyalphabetic substitution cipher** that improves upon the simplicity of the [[Caesar Cipher]] by using a keyword to determine the shift for each letter in the plaintext. This makes it more secure than the Caesar Cipher, as it introduces variability in the encryption process.

---
#### How the Vigenère Cipher Works

1. **Key Selection**:
    - A keyword is chosen (e.g., "KEY").
    - The keyword is repeated to match the length of the plaintext.
        
2. **Encryption**:
    - Each letter in the plaintext is shifted by the corresponding letter in the keyword.
    - The shift value for each letter is determined by its position in the alphabet (A=0, B=1, ..., Z=25).
    - Formula:
        $C=(P+K) mod  26$
        - C = Ciphertext letter
        - P = Plaintext letter
        - K = Key letter
            
3. **Decryption**:
    - The same keyword is used to reverse the process.
    - Formula:
        $P=(C−K) mod 26$

---

#### Example of Vigenère Cipher

- **Plaintext**: `HELLO`
    
- **Key**: `KEY` (repeated to match the length of the plaintext: `KEYKE`)
    
- **Encryption**:
    - H (7) + K (10) = R (17)
    - E (4) + E (4) = I (8)
    - L (11) + Y (24) = J (9) (since 11 + 24 = 35, and 35 mod 26 = 9)
    - L (11) + K (10) = V (21)
    - O (14) + E (4) = S (18)
        
- **Ciphertext**: `RIJVS`
    

---

#### Key Characteristics

1. **Polyalphabetic**:
    
    - Uses multiple Caesar Ciphers based on the keyword, making it more secure than a simple substitution cipher.
        
2. **Key Repetition**:
    
    - The keyword is repeated to match the length of the plaintext.
        
3. **Case Insensitivity**:
    
    - Works for both uppercase and lowercase letters.
        
4. **Reversibility**:
    
    - The same keyword can be used to encrypt and decrypt.
        

---

#### Advantages of the Vigenère Cipher

1. **Improved Security**:
    
    - The use of a keyword introduces variability, making frequency analysis more difficult.
        
2. **Flexibility**:
    
    - The keyword can be of any length, allowing for customization.
        

---

#### Disadvantages of the Vigenère Cipher

1. **Key Management**:
    
    - The security of the cipher depends on the secrecy of the keyword.
        
2. **Vulnerable to Known Plaintext Attacks**:
    
    - If part of the plaintext is known, the keyword can be deduced.
        
3. **Not Unbreakable**:
    
    - Advanced techniques like the Kasiski examination or statistical analysis can break the cipher.