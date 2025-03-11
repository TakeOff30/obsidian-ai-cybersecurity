> [!quote]
> ***Cybersecurity relates to protecting digital data***: "
> is the practice of protecting systems, networks, and programs from digital attacks and the practice of defending computers, server, mobile devices, electronic systems, networks, and data from malicious attacks. technologies, practices and policies for preventing cyberattacks or mitigating their impact."

**CYBER** means :
- involving, using, or relating to computers, especially the internet
- of relating to, or involving computers or computer networks (such as the Internet)
### MOTIVATION
if two user use a public channel to communicate important information a third part (eve) can intercept the message, read it and eventually modify it. We want to avoid these situations, thus ensure [[CONFIDENTIALITY]], and ensure the [[INTEGRITY]] of the messages sends across the public channel and the availability of it.
![[Pasted image 20250311163918.png]]
* [[INTEGRITY]], guarantees that data remains unalterated except by authorized parties. achieved via:
	* error detection/correction
	* crypthographic checksums
* AVAILABILITY, ensures that resources are readily accessible for authorized parties.
* [[CONFIDENTIALITY]], ensuring that only authorized parties can access non-public information. implemented through:
	* data encryption
	* access control mechanism
--- 
# Security Goal:
different security goals are achieved through different approaches like:
1. **AUTHENTICATION**: Verifying the identity of an entity if it is genuine 
	*Example*: 
	- Entity authentication 
	- Data origin authentication
2. **AUTHORIZATION**: Resources are accessible only by authorized entities 
	*Example*: 
	* Access control 
	* Access restriction
3. **ACCOUNTABILITY**: Ability to identify entities responsible for past actions 
	*Example*: 
	* Audit log
4. **AVAILABILITY**: Resources are readily accessible for authorized parties 
	*Example*:
	* Redundant system
5. **NON-REPUDIATION :** unable to refute responsibility 
6. **FORGEABILITY** : ability to create valid messages / signatures 
7. **FORWARD SECRECY** : retaining security of previous 
8. transactions 
9. **FUTURE SECRECY** : self-healing after compromise
---
# Cryptographic Primitives
*Cryptography is a fundamental building block for cybersecurity*

1. ***Encryption / decryption*** : AES, RSA, ECC, . . .
2. ***Key exchange / agreemen***t : Diffie–Hellman, . . . 
3. ***Message authentication code*** : HMAC, Poly1305, . . . 
4. ***Digital signature*** : Schnorr, ECDSA, . . .
5. ***Cryptographic hash function*** : SHA, Keccak, . . .

---
# course outline:
Confidentiality 
1. [[Historical Cipher]]
2. modern cipher 
3. real-world application 
Integrity 
4. Hash, 
5. message authentication code , 
6. digital signature 
Computer Security 
7. Buffer overflow, 
8. side-channel leakage
9. transient execution 
Access Control 
10. Password 
11. authentication 
12. access control 
13. Network security  
14. web security 