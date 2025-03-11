Generalization of Caesar cipher (also ROT13)
Assume: lowercase English alphabet for message and ciphertext space.
the Key should be:  k ∈ {0, 1, . . . , 25}, that indicates the rotate positions (how much big is the step between the character and its encryption).

Example: 
* k = 3 : Caesar cipher 
* k = 10 : this is an example → drsc sc kx ohkwzvo
![[Pasted image 20250311183705.png]]

Problems:
1. Small key space; |K| = 26 
2. Same letter maps to same cipher