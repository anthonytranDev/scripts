# Introduction

> Note that the `bash` and `zsh` shell are both separate in shell script syntax

## Command Prompt

The Shell issues a command prompt (usually $), where you can type your input, which is then executed when you hit the Enter key. The output or the result is thereafter displayed on the terminal.

The Shell wraps around the delicate interior of an Operating system protecting it from accidental damage

## Bourne Shell

The Bourne Shell: The prompt for this shell is $ and its derivatives are listed below:

- POSIX shell also is known as sh
- Korn Shell also knew as sh
- Bourne Again SHell also knew as bash (most popular)

## What is a script?
At their core, scripts are just plain text files. 

## Shell Scripting

Shell scripting is writing a series of command for the shell to execute. It can combine lengthy and repetitive sequences of commands into a single and simple script, which can be stored and executed anytime. This reduces the effort required by the end user.

Let us understand the steps in creating a Shell Script

1.  Name  script file with extension .sh
2. Start the script with #! /bin/sh
3. Write some code.
4. Save the script file as filename.sh
5. For executing the script type bash filename.sh

### Shebang

"#!" is an operator called shebang which directs the script to the interpreter location. So, if we use"#! /bin/sh" the script gets directed to the bourne-shell.

## References
[Introduction to shell-scripting](https://www.guru99.com/introduction-to-shell-scripting.html#1)