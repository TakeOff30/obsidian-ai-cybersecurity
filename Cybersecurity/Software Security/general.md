vulnerability definition: weakness that can be explioted by an attacker which allows him to do something he is not suposed to. also known as attack surface

if i use malloc and do not check the dimension of an input then the attacker can access my memory (buffer overflow)

information leakege: some information that should be private can be used by the attacker to execute an attack (hardcoded password)

race condition

invalid data processing

secure programming, write software to be protected from vulnerabilities, reduce attack surface

reliable softaware, quality software consistent in quality and performance in time

secure software, consistent in time also in hostile environments

security principles:
	learn by mistakes, when a problem is found we recognize it and learn from it by replicating, preventing it
	minimize attack surface, dont use dependency not needed
	use defense in depth, dont rely on other systems

defensive programming
	programming technique to guarantee by design that a software can function also under attack
	focus on the entire lifetime of the software
	check for preconditions for a function

secure software development
	starting from the design phase we should do threat modelling
	in the testing phase we should do pentesting at the software
	when shipped we should establish who should act in case on need 

static and dynamic analysis
	static analysis, on source code or object code
	dynamic analysis, when the program is running

obfuscator to prevent from decompilation


