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

## Versions
**zsh** - zsh 5.7.1 (x86_64-apple-darwin19.0)
**iterm2** - iterm2: 3.3.6 (auto_updates)

Zsh is a UNIX command interpreter (shell) usable as an interactive login shell and as a shell
script command processor. 

### Installing zsh shell
`brew install zsh`

### Installing oh-my-zsh
`sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`

### Changing oh-my-zsh config
This includes it's look and feel of the terminal in iterm2

`code ~/.zshrc`

## zsh Roadmap
### Completion
Shell can be used to complete the following usernames, hostnames, and even remote
paths in arguments to scp, and so on

#### Two completion systems
- **compctl** - (named after the builtin command that serves as its complete and only user interface), and a new one, referred to as
- **compsys** - organized as library of builtin and user-defined functions. The new system is more customizable and
is supplied with completions for many commonly used commands

### Pattern Matching
Described as globbing
- **\*\*** -  for matching over multiple directories
- **|** - for matching either of two alternatives
- **~, ^** - the ability to exclude patterns from matching when the EXTENDED_GLOB option is
set
- **(...)** - glob qualifiers, included in parentheses at the end of the pattern, which select files
by type (such as directories) or attribute (such as size).

### Programming
The most convenient way of adding enhancements to the shell is typically by writing a shell
function and arranging for it to be autoloaded.

## Change the use of either bash or zsh in terminal

Simple use `sh` for bash and `zsh` for zsh

## Changing the default shell to zsh

```chsh -s /bin/zsh```

## Differences between zsh and bash
- Has different prompts
- Difference configuration
- Offers better configuration for auto-completion
- Arrays and associative arrays (dictionaries)

## Miscellaneous
### When using scripts
There is one exception where I would now recommend to use /bin/sh for your scripts.
The Recovery system does not contain the /bin/zsh shell.

## References
[Introduction to shell-scripting](https://www.guru99.com/introduction-to-shell-scripting.html#1)

[How to Configure your macOs Terminal with zsh like a pro](https://www.freecodecamp.org/news/how-to-configure-your-macos-terminal-with-zsh-like-a-pro-c0ab3f3c1156/)

[Moving to zsh](https://scriptingosx.com/2019/06/moving-to-zsh/)