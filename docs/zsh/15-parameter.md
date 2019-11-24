# Parameters

## Positional parameters
Below is an extract from the Bash Manual

In short in #!/bin/sh
- `$0` is the cwd directory
- `$1..n` are one or more arguments supplied by the prompt


ARGUMENTS
If arguments remain after option processing, and neither the -c nor the -s option has been supplied, the first argument is assumed to be the name of a file containing shell commands. If bash is invoked in this fashion, $0 is set to the name of the file, and the positional parame- ters are set to the remaining arguments.

[How to exec but keeping the same argv0](https://stackoverflow.com/questions/16111455/how-to-exec-but-keeping-the-same-argv0)