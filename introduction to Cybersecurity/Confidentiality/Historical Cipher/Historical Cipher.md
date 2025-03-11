*Cipher is important to secure communications transmitted over public channels*. There could be some third part in the middle of the communication that can spy the data or even more modified them by impersonate one of the 2 actors involved in the communication (Alice or Bob).
![[Pasted image 20250311173705.png]]

## Terminology
* **ENCODE / DECODE**:  is the conversion of data from one format into another for usability (It makes the message less prone to error due to noise in the channel for example )
	* No secret key involved → anyone can inverse knowing the algorithm 
	* Example: ASCII, unicode, Base64 
	* Encoding provides no security 
* **ENCRYPT / DECRYPT**: is the transformation of plaintext into ciphertext via secret key for security 
	* Non-trivial to reverse without knowing the key 
	* Example: AES, RSA, ECC
	* Encrypt then encode does not add more security
# Cryptography vs Steganography 
- **CRYPTOGRAPHY**:  Transform information to avoid comprehension. Knowing a message is transmitted but cannot extracting it
- **STEGANOGRAPHY**:  Hide information to avoid detection. Not knowing that the information is there. So, the attacker doesn't even know that the key is under his eyes.
	*Example*:
	- Tattooed message on shaved head 
	- Hide messages in images, videos, sounds, etc
# Kerckhoffs’ principle 

> [!IMPORTANT]
> Cryptosystem should remain secure even everything else (e.g., encryption algorithm) is a public knowledge but the secret key

* Contrast with security through obscurity
* Difficult to keep the entire design/algorithm secret because there are many reverse-engineering techniques to uncover the schemes.
* Creating new schemes is more difficult than generating new keys 
* Public schemes allow more people to cryptanalyze and understand how much secure is the system.

To summarize, Kerckhoffs's principle states that a cryptographic system should remain secure even if all its design details are publicly known. Its security must depend solely on the secrecy of the cryptographic key, rather than on keeping the algorithm or system architecture confidential. This ensures resilience against insider threats, facilitates peer review for identifying vulnerabilities, and supports long-term security by allowing updates or key changes without redesigning the entire system.

# Attackers
###  Goals: 
* ***Plaintext recovery*** : Given a ciphertext, the attacker attempts to obtain the corresponding plaintext. This process must be repeated for each message.
* ***Key recovery*** : The attacker aims to discover the encryption key, which would allow them to decrypt all messages encrypted with that key.
### Abilities:
**COMPUTATIONAL POWER:**
* Unlimited computational power: The attacker can perform [[Exhaustive Search]] (BRUTE FORCE ATTACK) by trying all possible keys until the correct one is found. This is theoretical, as real-world attackers are always constrained by practical limitations
* Finite computational power: The attacker has limited resources (time, memory, processing power), so they must use optimized strategies like known cryptanalytic attacks (e.g., differential cryptanalysis, linear cryptanalysis, side-channel attacks) instead of brute force.

**ACCESS TO PHYSICAL IMPLEMENTATION**: Attackers might exploit vulnerabilities in hardware or software implementations of cryptographic systems.

Possible physical attacks include:
- ***Side-channel attacks***: Observing power consumption, electromagnetic radiation, or execution time to infer key information.
- ***Fault injection attacks**: I*ntentionally disturbing the system (e.g., using laser pulses, voltage fluctuations) to cause faults and extract secret information.
- ***Cold boot attacks**:* Extracting cryptographic keys from RAM after a system reboot.
- ***Reverse engineering**:* Disassembling cryptographic hardware or software to understand its workings and identify weaknesses.
## Attacks model
the attacks model depends on what types of data the attacker has access to: 
- ***Ciphertext-only attack***: The attacker only has access to ciphertexts and tries to deduce information about the plaintext or key.
- ***Known-plaintext attack***: The attacker has access to some plaintext-ciphertext pairs and uses them to infer the key or decrypt new messages.
- ***Chosen-plaintext attack**:* The attacker can choose plaintexts and obtain their corresponding ciphertexts thanks to the access of the encryption oracle, allowing analysis of how the encryption behaves.
- ***Chosen-ciphertext attack**:* The attacker can choose ciphertexts and obtain their corresponding plaintexts thanks to the access to the decryption oracle, potentially identifying weaknesses in the decryption process (e.g., Bleichenbacher’s RSA attack).

# Famous Historical Cipher

 [[Caeser Cipher]] → [[Shift Cipher]]
 