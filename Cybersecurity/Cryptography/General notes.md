secure padding: usa ecb critta sempre uguale, usa 16 caratteri codificando indipendentemente ogni blocco, AES_ECB, bruteforce cercando ad ogni step di individuare uno dei caratteri appendati della flag.

once too many: mtp tool 

redacted: AES_CBC, a blocchi faccio lo xor con ECB avendo il plaintext

two flags: xor tra le 2 immagini di partenza

notadmin: bitflip su is_admin=0, cerco di fare lo xor tra iv e iv stesso per ottenere admin=1

padding oracle: attack, uso il secondo blocco per decifrare quello successivo

predictable iv: creare il token admin, utilizzare iv per anti-xorare

des oracle