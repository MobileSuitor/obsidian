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
- 