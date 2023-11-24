Sample project on how the shell work.

This repository will contain several trial case before the release of the actual project
Collaboration is welcomed. Bare in mind all programs MUST past the below test suite before pushing to github.


Test suite

$ echo "Today is \$(date)." | ./myshell
_Expected output: Today is <current_date_and_time>._
$ ls non_existent_directory && echo "Directory exists." || echo "Directory does not exist." > output.txt
_Expected output: Directory does not exist._
$ (ls -l | grep ".txt" &); sleep 1; echo "Background process running." | ./myshell
_Expected output: Background process running._
$ echo -e "for i in {1..5}; do echo \$i; done" | ./myshell
_Expected output: 1\n2\n3\n4\n5_
$ echo "This is a test." > output.txt 2>&1 | ./myshell
_Expected output: (No output, but 'output.txt' should contain "This is a test.")_
$ echo -e "function greet() { echo 'Hello, ' \$1 '!'; }\ngreet World" | ./myshell
_Expected output: Hello, World!_
$ echo "Current directory is: \$(pwd)" | ./myshell
_Expected output: Current directory is: <current_directory_path>_
$ (echo "First" | cat - <(echo "Second")) | sort | uniq
_Expected output: First\nSecond_


