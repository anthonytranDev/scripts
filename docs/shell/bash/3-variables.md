# Variables

To process data, data must be kept in the computer’s memory. Memory is divided into small locations, and each location had a unique number called memory address, which is used to hold data.

In Linux Shell Scripting, there are two types of variable:
- **System variables** — Created and maintained by Linux itself. This type of variable defined in CAPITAL LETTERS.

- **User-defined variables** — Created and maintained by the user. This type of variable defined in lower letters.

Some important system variables
- HOME — Holds home directory path
- OSTYPE — Holds OS type
- USERNAME – Holds username who is currently logged in to the machine

## Defining and Accessing Variables

```
# Syntax to define a variable
name=abc
To access user-defined variables use the following syntax:
```
```
# Syntax to access a variable
$name
```
```
#Syntax to print a variable
echo "My name is $name"
```

## Double Quotes, Single Quotes, Back ticks

Single quotes (‘) : Anything inside single quotes will be a string. See example:

Double Quotes (“) : Anything inside double quotes will be string except \ and $. See example

Left Quotes (`): Anything enclosed in left quotes will be treated as an executable command. See examples


## References

https://medium.com/tech-tajawal/writing-shell-scripts-the-beginners-guide-4778e2c4f609