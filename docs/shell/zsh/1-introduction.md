# Introduction

## Versions
**zsh** - zsh 5.7.1 (x86_64-apple-darwin19.0)
**iterm2** - iterm2: 3.3.6 (auto_updates)

Zsh is a UNIX command interpreter (shell) usable as an interactive login shell and as a shell
script command processor. 

## Setting up the shell

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

## References
[How to Configure your macOs Terminal with zsh like a pro](https://www.freecodecamp.org/news/how-to-configure-your-macos-terminal-with-zsh-like-a-pro-c0ab3f3c1156/)