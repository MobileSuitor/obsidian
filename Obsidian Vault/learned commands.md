- ==2>== - redirects error messages to a file
	- useful for logging error messages, troubleshooting and record keeping
- ==tree== - tool that helps visualize the structure of directories and subdirectories in a tree-like format
	- requires installation with ==sudo apt -f install tree -y==
	- ==tree -L 1 /== displays the structure of the root directory with a depth of one level
- ==less== - view contents of a file or output in a scrollable manner without opening in an editor
	- use / followed by keyword to search output
- ==$(command)== - captures output of a command and uses it as part of another command
	- ==output=$(ls)
	  echo "The files in the current directory are: " $output== - ls command is executed, output of ls is captured and stored in output variable, output variable is used to display list of files