matematica modulare
	congruenza modulo n
		a congruente mod n b se n divide a-b
			simmetria: a con a
			riflessiva: a con b allora b con a
			transitività: a con b b con c allora a con c
			a1 con a2
			b1 con b2
			allora
			a1+b1 con a2+b2
		classi di equivalenza 
		gruppo (insieme, operazione binaria), gli elementi sono chiusi rispetto al gruppo.
			le proprietà garantite nel gruppo sono associatività, la presenza di un elemento neutro e l'operazione identità
		dato a in Z/nZ, esiterà un inverso moltiplicativo se e solo se il gcd(a,b)=1, quindi restringiamo l'insieme dei numeri considerati ai numeri coprimi con n
		bezout: comunque presi due numeri interi e dato d=gcd(a,b) allora esiste x,y tali che ax+by=d
		funzione di eulero è il numero di numeri minori di n e coprimi con n
		difficolta a fattorizzare è la base di RSA
		numeri generatori generano tutti gli elementi del gruppo moltiplicativo
		ordine del gruppo=cardinalità del gruppo
		gruppo ciclico è generabile da un suo elemento
		teorema fondamentale dei gruppi ciclici, se il nostro gruppo G è ciclico allora ogni suo sottogruppo è ciclico e se n è l'ordine di G allora l'ordine di ogni sottogruppo di G divide n. Per ogni ordine esiste un sottogruppo
		teorema di Lagrange, se H è un sottogruppo di G l'ordine di H divide G.
		teorema di Eulero, per ogni coppia di interi positivi coprimi tra loro abbiamo che a elevato a phi di n è congruente a 1
		piccolo teorema di Fermat, dato p primo per ogni intero abbiamo che a alla p è congruente ad a modulo p
		crt, dati un insieme di numeri interi ad a due coprimi tra loro e dati r numeri interi esiste una soluzione al sistema di congruenze
		
condizioni che rendono un codice inviolabile:
- una chiave lunga quanto il messaggio
- algoritmi pseudo casuali
- chiave utilizzata una volta sola

cifratura a chiave simmetrica, uso la stessa chiave per cifrare e decifrare:
- gli utenti devono scambiarsi la chiave unica e sicura

glossario:
- plain text (P)
- cipher, algoritmo di cifratura
- ciphertext messaggio cifrato
- secret key, chiave segreta di cifratura
- algoritmo di decifratura (D)

l'algoritmo di cifratura è pubblico e noto, la potenza della cifratura sta nella chiave


attaccante cerca di interpretare i dati sul canale di comunicazione ed estrapola una stima che si avvicina più o meno al messaggio originale

l'algoritmo, data una minima differenza tra due messaggi originali, la loro cifratura deve essere completamente lontana (di almeno il 50%) da uno all'altro.

trasposizione

sostituzione

cifratura simmetrica (chiave unica), computazione leggera, per sistemi real time

cifratura asimmetrica (chiave pubblica/chiave privata), computazioni pesanti

cifratura a blocco, cifratura a flusso

se utilizzo la stessa chiave 2 volte, facendo l'and delle 2 y è equivalente all'AND dei messaggi originali

unconditional security, impossibile decifrare il messaggi senza chiave, garantita solo da OTP da attacchi passivi (attaccante osserva e basta i canali di comunicazione, i dati non possono essere cambiati)

chiave simmetrica AES
chiave privata RSA

crittografia quantistica, leggi della fisica proteggono l'informazione, ragiona in termini probabilistici, grazie al principio di indeterminazione posso capire se il mio canale quantistico viene violato











