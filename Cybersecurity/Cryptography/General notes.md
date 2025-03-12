secure padding: usa ecb critta sempre uguale, usa 16 caratteri codificando indipendentemente ogni blocco, AES_ECB, bruteforce cercando ad ogni step di individuare uno dei caratteri appendati della flag.

once too many: mtp tool 

redacted: AES_CBC, a blocchi faccio lo xor con ECB avendo il plaintext

two flags: xor tra le 2 immagini di partenza

notadmin: bitflip su is_admin=0, cerco di fare lo xor tra iv e iv stesso per ottenere admin=1

padding oracle: attack, uso il secondo blocco per decifrare quello successivo

predictable iv: creare il token admin, utilizzare iv per anti-xorare

des oracle

we want to secure communiction over public channels, to pevent from spying, modifying, impersonation of parties 

encode != encrypt
ascii != RSA

steganography, hide messages

kerchoff's principle, difficult to hide the algorithms, encryption should not rely on it
by keeping the algorithm public we can also allow more people to secure it

brute-force attacks to try every possible key

cipher text only attack: only see ciphers and wanna get the message
known plaintext attack: have plaintext-ciphertext pairs
chosen plaintext attack: have access to encryption oracle
chosen ciphertext attack: have access to decryption oracle

ceaser cipher: ROT13, shift cipher which has 13 as the number of rotations.

vigenere cipher: poly alphabetic shift cipher
i select a string to be the key and shift each letter by adding the index of the letter of the key to the plaintext

perfect secrecy: 
perfect indistinguishibilty: probability of guessing is 1/2
cannot understand if a message has m1 as plaintext or m2

one time pad: the length of the key should be the same of the message



