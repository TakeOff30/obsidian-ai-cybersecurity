Time-based blind [[SQL injection]] exploits the timing differences in database responses to infer information. 

The attacker injects SQL code that causes the database to pause or sleep for a specific duration based on a condition. By observing the response time, the attacker can determine whether the condition is true or false. 

An injected input might look something like **' AND IF((SELECT SUBSTRING(password, 1, 1) FROM users WHERE username = 'admin') = 'a', SLEEP(5), 0) --**. 
This injected code instructs the database to sleep for 5 seconds if the first character of the admin's password is "a". By systematically testing different characters and positions, the attacker can reconstruct the entire password, even without seeing any direct output from the database.