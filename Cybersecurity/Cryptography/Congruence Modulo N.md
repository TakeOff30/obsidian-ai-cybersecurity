"Two integers, a and b, are congruent modulo n (written a ≡ b (mod n)) if their difference (a - b) is divisible by n. In other words, a and b have the same remainder when divided by n."

Congruence modulo n is an equivalence relation, meaning it satisfies the following properties:

- Reflexivity: a ≡ a (mod n)
    
- Symmetry: If a ≡ b (mod n), then b ≡ a (mod n)
    
- Transitivity: If a ≡ b (mod n) and b ≡ c (mod n), then a ≡ c (mod n)

Properties: Important properties for cryptographic applications:
- If a ≡ b (mod n) and c ≡ d (mod n), then:
	- a + c ≡ b + d (mod n)
	- a - c ≡ b - d (mod n)
	- a * c ≡ b * d (mod n)
		
Allows us to treat congruent numbers as equivalent within a specific context (modulo n). This simplifies calculations and is essential for cryptographic operations.
