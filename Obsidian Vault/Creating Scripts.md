<u>/bin vs personal ~/bin directory:</u>
-  /bin
	- a system directory containing essential commands and utilities for the linux OS
	- should not be modified
- ~/bin
	- a directory in your personal home directory where you can store your own custom scripts
------------------------
<u>Making Scripts</u>
- use IO redirection to create a new script with the shebang:
	- ==echo '#! /bin/bash' > script1
- you can use ==echo== and >> redirection to append lines to the script, or write it out manually in nano text editor'
- test run script with ==bash ./script1==

---------------
<u>Running Scritps</u>
- scripts that contain sudo commands will need to prompt the user for a password
	- if you want to run a script that contains sudo commands autonomously without any user input, run the script as root with sudo
- executing scripts as sudo/with root privileges
	- make script executable with chmod u+x \<script name>
	- issue command as sudo ./\<script name>
	- if you are still getting an error, you may need to edit sudoers:
		- as root, issue ==🟣visudo -f /etc/sudoers.d/USERNAME==
		- add ==🟣USERNAME ALL=(ALL:ALL) ALL==
		- set passwords with passwd

--------------
<u>Testing Scripts</u>
- check whether a command in a script worked by looking at its exit status:
	==🟣if [ $? -eq 0 ]; then
		# success
	else 
		# failure
	fi==
------------------
<u>Iterating through arrays with for loops</u>
- defining a list or array: list=("item1" "item2")
- iterating: ==🟣for item in "${list\[@]}" do==
	- curly braces are required when working with arrays so the shell doesn't confuse the brackets with regular text
	- \[@] notation tells bash to grab all elements in the array