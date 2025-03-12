
The **One-Time Pad** (OTP) is a [[symmetric encryption]] technique that provides [[Perfect Secrecy]] when used correctly. It is one of the most secure encryption methods, but its practical use is limited due to certain constraints.

#### Key Principle

- The **key** used in a one-time pad must be:
    
    1. **Truly random**: The key should be generated using a cryptographically secure random number generator.
        
    2. **As long as the message**: The length of the key must match the length of the plaintext message exactly.
        
    3. **Used only once**: The key should never be reused for another message. Reusing the key compromises security.
        

#### How It Works

1. **Encryption**:
    
    - The plaintext message is combined with the key using a bitwise XOR operation.
        
    - Formula: `Ciphertext = Plaintext ⊕ Key`
        
    - Example:
        
        - Plaintext: `HELLO` (in binary: `01001000 01000101 01001100 01001100 01001111`)
            
        - Key: `SECRET` (in binary: `01010011 01000101 01000011 01010010 01000101`)
            
        - Ciphertext: `00011011 00000000 00001111 00011110 00001010`
            
2. **Decryption**:
    
    - The ciphertext is combined with the same key using XOR to recover the plaintext.
        
    - Formula: `Plaintext = Ciphertext ⊕ Key`
        

#### Advantages

- **Perfect Secrecy**: If the key is truly random, as long as the message, and used only once, the one-time pad is theoretically unbreakable.
    
- **No Pattern**: Since the key is random, the ciphertext reveals no information about the plaintext.
    

#### Disadvantages

- **Key Distribution**: The key must be securely shared between the sender and receiver, which is challenging in practice.
    
- **Key Length**: The key must be as long as the message, making it impractical for large messages.
    
- **Key Management**: Keys cannot be reused, requiring a new key for every message.
    

#### Practical Use Cases

- Historically used for sensitive communications, such as diplomatic or military messages.
    
- Modern applications are rare due to the impracticality of key distribution and management.