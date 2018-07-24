Shell Commands
Shell commands come in several forms:

Commands without arguments:

  $ pwd
Commands with arguments:

  $ sort tests/sample.txt
Operators with single commands:

  $ sort < foo.txt
Operators joining multiple commands

  $ grep derp foo.txt | wc -l
In your shell assignments, you need to handle seven operators:

Redirect input: sort < foo.txt
Redirect output: sort foo.txt > output.txt
Pipe: sort foo.txt | uniq
Background: sleep 10 &
And: true && echo one
Or: true || echo one
Semicolon: echo one; echo two
Tokenizing Shell Commands
In this assignment, you will write a program that reads single line shell commands, splits them into tokens, and prints out one token per line.

Although your tokenization function should handle arbitrary size input, your code that actually reads in strings can assume that input lines are no longer than 100 characters.

You can think of tokens as coming in four types:

Command names.
Command arguments.
Shell operators.
Non-command operator arguments.
Spaces that appear in a command are not tokens, although they may separate tokens.

Example interaction:

bash$ ./tokens
tokens$ echo one; echo two
echo
one
;
echo
two
tokens$ sort foo.txt | uniq
sort
foo.txt
|
uniq
tokens$ ^D
bash$
In the above interaction, "^D" is used to indicate Ctrl+D, which sends end-of-file. The "tokens$ " prompt is optional, but is specifically recognized by the test scripts - other prompts may not work.

