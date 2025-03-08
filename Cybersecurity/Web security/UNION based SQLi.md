A UNION-based [[SQL injection]] leverages the UNION SQL keyword to combine the results of the original query with a second, attacker-controlled query. 

For instance, if the application is displaying a list of product names and prices based on a user-provided category, an attacker could inject a UNION clause to retrieve sensitive data from other tables. 
The injected input might look like **Category' UNION SELECT username, password FROM users --** . 
This modified query would then retrieve usernames and passwords from the users table and display them alongside the legitimate product data, effectively leaking sensitive information.