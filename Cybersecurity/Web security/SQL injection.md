SQL injection is a [[Code Injection]] technique that exploits vulnerabilities in an application's database interaction. 
It occurs when user-supplied input is improperly incorporated into a SQL query without sufficient sanitization, allowing an attacker to insert malicious SQL code that can manipulate the database. 

For example, a website form might ask for a username, and if the application doesn't properly sanitize this input, an attacker could enter a malicious username that modifies the query to bypass authentication or extract data. 
Instead of a simple username, they might enter something like **' OR '1'='1** which, if directly inserted into the SQL query, would create a condition that is always true, potentially granting them unauthorized access.