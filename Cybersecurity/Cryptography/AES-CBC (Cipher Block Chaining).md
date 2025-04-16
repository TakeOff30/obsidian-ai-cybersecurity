
#### Overview
- **AES-CBC** is a widely used symmetric encryption algorithm that combines the **[[AES]] (Advanced Encryption Standard)** algorithm with the **CBC (Cipher Block Chaining)** mode of operation.
- It is a **block cipher**, meaning it encrypts data in fixed-size blocks (128 bits for AES).
- **Symmetric encryption** means the same key is used for both encryption and decryption.
- **CBC mode** introduces chaining, where each block of plaintext is XORed with the previous ciphertext block before encryption, ensuring that identical plaintext blocks produce different ciphertext blocks.

---

### Key Concepts

#### 1. **AES (Advanced Encryption Standard)**
- AES is a symmetric encryption algorithm standardized by NIST in 2001.
- It operates on **128-bit blocks** and supports key sizes of **128, 192, or 256 bits**.
- AES is highly secure and efficient, making it the most widely used encryption algorithm.

#### 2. **CBC (Cipher Block Chaining)**
- CBC is a mode of operation for block ciphers like AES.
- It introduces **chaining**, where each plaintext block is XORed with the previous ciphertext block before encryption.
- This ensures that identical plaintext blocks produce different ciphertext blocks, adding **diffusion** and **randomness** to the encryption process.
#### 3. **Initialization Vector (IV)**
- A **random value** used to initialize the encryption process.
- The IV ensures that the same plaintext encrypted with the same key produces different ciphertexts.
- The IV must be:
    - **Unique** for each encryption operation.
    - **Random** to ensure security.
    - **Transmitted securely** along with the ciphertext (typically prepended to the ciphertext).
#### 4. **Padding**
- AES operates on fixed-size blocks (128 bits). If the plaintext is not a multiple of 128 bits, it must be **padded**.
- Common padding schemes include **PKCS7**, which adds bytes to the plaintext to make its length a multiple of the block size.
- During decryption, the padding is removed to recover the original plaintext.

---

### Encryption Process

1. **Generate IV**:
    
    - A unique, random IV is generated for each encryption operation.
        
    - The IV is typically 128 bits (16 bytes) long, matching the AES block size.
        
2. **Padding**:
    
    - The plaintext is padded to ensure its length is a multiple of 128 bits (16 bytes).
        
    - For example, using PKCS7 padding, if the plaintext is 15 bytes long, 1 byte of padding (`0x01`) is added.
        
3. **Encryption**:
    
    - The plaintext is divided into 128-bit blocks.
        
    - For the first block:
        
        - XOR the plaintext block with the IV.
            
        - Encrypt the result using the AES algorithm with the secret key.
            
        - The output is the first ciphertext block.
            
    - For subsequent blocks:
        
        - XOR the plaintext block with the previous ciphertext block.
            
        - Encrypt the result using the AES algorithm.
            
        - The output is the next ciphertext block.
            
4. **Output**:
    
    - The IV is prepended to the ciphertext (since it is needed for decryption).
        
    - The final ciphertext consists of the IV followed by the encrypted blocks.
        

---

### Decryption Process

1. **Extract IV**:
    
    - The IV is extracted from the beginning of the ciphertext.
        
2. **Decryption**:
    
    - The ciphertext is divided into 128-bit blocks.
        
    - For the first block:
        
        - Decrypt the ciphertext block using the AES algorithm with the secret key.
            
        - XOR the result with the IV to recover the first plaintext block.
            
    - For subsequent blocks:
        
        - Decrypt the ciphertext block using the AES algorithm.
            
        - XOR the result with the previous ciphertext block to recover the plaintext block.
            
3. **Remove Padding**:
    
    - After decrypting all blocks, the padding is removed to recover the original plaintext.
        

---

### Advantages of AES-CBC

1. **Security**:
    
    - CBC mode introduces **diffusion**, ensuring that each ciphertext block depends on all previous blocks.
        
    - This makes it resistant to certain types of cryptanalysis.
        
2. **Randomization**:
    
    - The use of a unique IV ensures that the same plaintext encrypted with the same key produces different ciphertexts.
        
3. **Wide Adoption**:
    
    - AES-CBC is widely used in protocols like TLS, SSL, and IPsec.
        

---

### Disadvantages of AES-CBC

1. **Error Propagation**:
    
    - Errors in one ciphertext block can affect the decryption of subsequent blocks.
        
    - For example, a single bit error in a ciphertext block will corrupt the corresponding plaintext block and the next block.
        
2. **No Parallelization**:
    
    - Encryption cannot be parallelized because each block depends on the previous one.
        
    - Decryption, however, can be parallelized since each ciphertext block is decrypted independently.
        
3. **Padding Oracle Attacks**:
    
    - If an attacker can determine whether padding is valid or not, they can exploit this to decrypt ciphertext (though this is mitigated in modern implementations).