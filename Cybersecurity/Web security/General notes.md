file disclosure: does not allow to only get some resource from a server but only perform attacks as code execution
sometimes, .git folder remains public
web-server misrouting
path traversal for exploits, /etc/passwd is always present if it is enabled i can search other files
appended path traversal, if there is an open instruction i can change the path and move in the directory
how to fix? normalize paths

server side request forgery 
allows attacker to send network request from the remote application

code and command injection

SQL injection
bypassing login: `' OR 1=1 --`
retrieveing the number of columns: `1 UNION SELECT 1,2,3` --> success means there are 3 columns. Can be done also with ORDER BY directive.
Usually with: `AND 1=0 UNION ...` we can disable the query written by the user and run our own injected query.
Goal is to find INFORMATION_SCHEMA from the victims database

blind SQL injection


