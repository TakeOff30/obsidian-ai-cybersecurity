TTP server used for secure exchange of session keys, but TTP is a single point of failure possibly vulnerable to DDoS attacks and others
TLS substitues automatically the key used for encryption
Perfect forward security
How to exchange keys in a secure way?
Diffie-Hellman -> A and B decide a big prime number p and a generator g such that g in {2,...,p-1}. 
A picks a number a in Zp={1,...,p-1}. It elevates g^a and sends it to B. B picks b in Zp and sends to A g^b mod p. Then A receives the number Yb, obtaines Yb^a mod p. B receives Ya and obtains Ya^b mod p. These 2 numbers are the same number and corresponds to the shared key.
a is the descrete logarithm of Ya in base g.

Eliptic curves enhance modern cryptographic protocols

Diffie-Hellman, even if it is secure from sniffing and passive attacks, is vulnerable to active attacks.
This are authentication problem while DH ensures confidentiality.

Public key encryption, each party generates 2 keys: one of these is private and known only to the specific party. RSA is the prime encryption protocol in this context.
With the private key everyone can sign its message with the private key ensuring authentication. Then MITM attacks are prevented. It is not used to cipher data but only keys to be exchanged. It complements DH.

RSA: pick p,q prime numbers, compute n=p * q, compute phi(n)=(p-1) * (q-1)
produce e such that gcd(e,phi(n))=1
calculate d=e * d mod phi(n)
i obtained public and private keys e, d

RSA can be used for ensuring autenticity by swapping the public and private keys in the process. A ciphers with its private key and B checks with A's public key. 