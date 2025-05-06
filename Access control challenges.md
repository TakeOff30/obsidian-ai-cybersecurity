3: The vulnerability consists in the system command executed by flag01 which executes the echo comand from our environment variables in PATH so i can either modify the echo command and cat the flag or write another echo command on top of the file to open a shell
echo "/bin/ssh" > echo to create a file with the command needed to open a shell
then i change the PATH variable and justapose to it the current directory. By doing this executing the program will search for the first echo it finds and that will be the one i created in the current directory


4: The vulnerability consists yet again in the system command that takes the $USER environment variable and prints it with echo but we can also change the value of the user variable and inject a command that closes the initial echo, opens a shell and then again executes an echo command to close the injection. This will open a shell with user permissions

6: use soft links to read the flag.txt file
