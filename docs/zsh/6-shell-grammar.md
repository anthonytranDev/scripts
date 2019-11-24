# Shell Grammar

## Simple Commands & Pipelines

**simple command** - is a sequence of optional parameter assignments followed by blank-separated words, with optional redirections interspersed

The first word is the command to be executed, and the remaining words, if any, are arguments to the command. If a command name is given, the parameter assignments modify the environment of the command when it is executed.

**pipeline** is either a simple command, or a sequence of two or more simple commands where each command is 


**Separated by**
- **‘|’** - the standard output of the first command is connected to the standard input of the next.
- **‘|&’** - shorthand for ‘2>&1 |’, which connects both the standard output and the standard error of the command to the standard input of the next
- **&&** - If two pipelines are separated by ‘&&’, the second pipeline is executed only if the first succeeds (returns a zero status).
- **||** - Both operators have equal precedence and are left associative. The value of the sublist is the value of the last pipeline executed.

**Proceeding operators**
- **!** - is the logical inverse of the value of the last command
- **coproc** it is executed as a coprocess; a two-way pipe is established
between it and the parent shell.

## Lists

- **list**
  - definition 1 - a set of any shell commands
  - definition 2 - is a sequence of zero or more sublists, in which each sublist is terminated by
    - ‘;’
    - ‘&’
    - ‘&|’
    - ‘&!’
    - a newline.

  This terminator may optionally be omitted from the last sublist in the list when the list appears as a complex command inside ‘(...)’ or ‘{...}’

When a sublist is terminated
by ‘;’ or newline, the shell waits for it to finish before executing the next sublist. If a sublist
is terminated by a ‘&’, ‘&|’, or ‘&!’, the shell executes the last pipeline in it in the background,

**Status Codes [Incomplete]**

Returning a zero status, means that the pipeline has been successfully executed

## Precommand Modifiers
which will alter how the command is interpreted. These modifiers are shell builtin commands with the exception of `nocorrect` which is a reserved word.

- **‘-’** - this command is executed with a ‘-’  prepended to its argv[0] string.
- **builtin** this command word is taken to be the name of a builtin command, rather than a
shell function or external command. Please use `man builtin`, for more details on built-in commands
  - **command** - The command word is taken to be the name of an external command, rather than a shell function or builtin **[???]**
  - **exec** - exec [ -cl ] [ -a argv0 ]
    - -c option clears the environment.
    - -l option is equivalent to the - precommand modifier, to treat the replacement command as a login shell; the command is executed with a - prepended to its argv[0] string. This flag has no effect if used together with the -a option.
    - -a option is used to specify explicitly the argv[0] string (the name of the command as seen by the process itself) to be used by the replacement command and is directly equivalent to setting a value for the ARGV0 environment variable.
  - **nocorrect** - spelling correction is not done on any of the words. This must appear before any other precommand modifier, as it is interpreted
  - **noglob** Filename generation (globbing) is not performed on any of the words

## Complex Commands
Zero **'0'** accounts as been true

Non-zero **'n'** accounts as been false, where is n is not zero
- [[ exp ]] Evaluates the conditional expression exp and return a zero exit status if it is true.
- ( list ) Execute list in a subshell. Traps set by the `trap` builtin are reset to their default
values while executing list.
- { list } Execute list.
- `if` list `then` list [ `elif` list `then` list ] ... [ `else` list ] `fi`
- `for` name ... [ `in` word ... ] term `do` list `done`
  -  If the ‘in word’ is omitted, use the positional parameters instead of the words.
- `for` (( `[expr1]` ; `[expr2]` ; `[expr3]` )) `do` list `done`
- `while` list `do` list `done`
- `until` list `do` list `done` - `until` is the opposite of `while`
- `repeat` word `do` list `done`
- `case` word `in` [ [(] pattern [ | pattern ] ... ) list `(;;|;&|;|)` ] ... `esac`
  -  unless the `SH_GLOB` option is set, the whole pattern with alternatives is treated by the shell as equivalent to a group of patterns within parentheses
  - If the list that is executed is terminated with `;&` rather than `;;`, the following list is also executed.
  - The rule for the terminator of the following list `;;`, `;&` or `;|` is applied unless the esac is reached.
  - If the list that is executed is terminated with ;| the shell continues to scan the patterns looking for the next match, executing the corresponding list, and applying the rule for the corresponding terminator ;;, ;& or ;|.
  -  Note that word is not re-expanded; all applicable patterns are tested with the same word.
- `select` name [ `in` word ... term ] `do` list `done`
  - where term is one or more newline or `;` to terminate the words. Print the set of words, each preceded by a number. If the in word is omitted, use the positional parameters **[???]**
- { try-list } `always` { always-list }
  - called a try block and always block
- `function` word ... [ () ] [ term ] { list }
  - word ... () [ term ] { list }
  - word ... () [ term ] command
  - where term is one or more newline or `;`.
  - In any of the forms above, a redirection may appear outside the function body, for example
    - func() { ... } 2>&1
    - This redirection is stored with the function and applied whenever the function is executed.
    - Any variables in the redirection are expanded at the point the function is executed, but outside the function scope.
  - setting traps **[???]**
- `time` [ pipeline ]
  - The pipeline is executed, and timing statistics are reported on the standard error in the form specified by the `TIMEFMT` parameter. If pipeline is omitted, print statistics about the shell process and its children.
- Additional tokens
  - break
  - continue
  - return

## Alternate Forms For Complex Commands
**[Section Missed out]**

## Reserved Words
The following words are recognized as reserved words when used as the first word of a command
unless quoted or disabled using disable -r:

```
do done esac then elif else fi for case if while function repeat time until
select coproc nocorrect foreach end ! [[ { } declare export float integer local
readonly typeset
``` 

Additionally, ‘}’ is recognized in any position if neither the IGNORE_BRACES option nor the
IGNORE_CLOSE_BRACES option is set.

## Errors
Read this section when one has time

## Aliasing
Every eligible **word** in the shell input is checked to see if there is an alias defined for it. 
If so;
- it is replaced by the text of the alias if it is in command position (if it could be the first word
of a simple command)
- or if the alias is global


- `alias` builtin; global aliases may be defined using the `-g` option to that builtin.
- A word is defined as:
  - Any plain string or glob pattern
  - Any quoted string, using any quoting method (note that the quotes must be part of the alias definition for this to be eligible)
  - Any parameter reference or command substitution
  - Any series of the foregoing, concatenated without whitespace or other tokens between them
  - Any reserved word (case, do, else, etc.)
  - With global aliasing, any command separator, any redirection operator, and ‘(’ or ‘)’ when not part of a glob pattern

## Quoting
Will look at this later on **[???]**

## Miscellaneous
If the option `SH_GLOB` is set for compatibility with other shells **[???]**