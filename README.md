Sample project on how the shell work.

This repository will contain several trial case before the release of the actual project
Collaboration is welcomed. Bare in mind all programs MUST past the below test suite before pushing to github.


Test suite

$ echo "Today is \$(date)." | ./myshell
# Expected output: Today is <current_date_and_time>.
$ ls non_existent_directory && echo "Directory exists." || echo "Directory does not exist." > output.txt
# Expected output: Directory does not exist.
$ (ls -l | grep ".txt" &); sleep 1; echo "Background process running." | ./myshell
# Expected output: Background process running.
$ echo -e "for i in {1..5}; do echo \$i; done" | ./myshell
# Expected output: 1\n2\n3\n4\n5
$ echo "This is a test." > output.txt 2>&1 | ./myshell
# Expected output: (No output, but 'output.txt' should contain "This is a test.")
$ echo -e "function greet() { echo 'Hello, ' \$1 '!'; }\ngreet World" | ./myshell
# Expected output: Hello, World!
$ echo "Current directory is: \$(pwd)" | ./myshell
# Expected output: Current directory is: <current_directory_path>
$ (echo "First" | cat - <(echo "Second")) | sort | uniq
# Expected output: First\nSecond


