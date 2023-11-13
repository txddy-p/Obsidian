Join me on my journey to master Linux
Learning something is cool and all but if you dont use it you're gonna forget, so whatever I learn I'll try my best to use it.

## **Using Find**

The find command is fantastic in the sense that it can be used both very simply or rather complex depending upon what it is you want to do exactly. However, let's stick to the fundamentals first.

```bash
find -name <name_of_file> #This is for when you know the file name
find -name *.extension #or anyother combo to locate files that meet that crit
```

## **Using Grep**

Another great utility that is a great one to learn about is the use of `grep`. The `grep` command allows us to search the contents of files for specific values that we are looking for.

```bash
grep "<something>" filename
```


# Linux operators
Linux. There are a few important operators that are worth noting. We'll cover the basics and break them down accordingly to bite-sized chunks.

At an overview, I'm going to be showcasing the following operators:

|  Symbol/Operator | Description  |
|---|---|
|&|This operator allows you to run commands in the background of your terminal.|
|&&|This operator allows you to combine multiple commands together in one line of your terminal.|
|>|This operator is a redirector - meaning that we can take the output from a command (such as using cat to output a file) and direct it elsewhere.|
|>>|This operator does the same function of the `>` operator but appends the output rather than replacing (meaning nothing is overwritten).|
|\|| This operator is used for piping. It sends data from one command to another|

## Operator "|"
Piping operator sends output from one command to another
  

## Operator "&"
The "&" shell operator allows us to execute a command and have it run in the background (such as this file copy) allowing us to do other things!

## Operator "&&"
Runs 2 commands one after the other, e.g. `command1 && command2`. However, it's worth noting that `command2` will only run if `command1` was successful.

## Operator ">"
This operator is what's known as an output redirector. What this essentially means is that we take the output from a command we run and send that output to somewhere else.

A great example of this is redirecting the output of the `echo` command that we learned in Task 4. Of course, running something such as `echo howdy` will return "howdy" back to our terminal — that isn't super useful. What we can do instead, is redirect "howdy" to something such as a new file!

Let's say we wanted to create a file named "welcome" with the message "hey". We can run `echo hey > welcome` where we want the file created with the contents "hey" like so:

Using the > Operator
```bash
echo hey > welcome
```

Using cat to output the "welcome" file
```bash
cat welcome hey
```

## Operator ">>"

This operator is also an output redirector like in the previous operator (`>`) we discussed. However, what makes this operator different is that rather than overwriting any contents within a file, for example, it instead just puts the output at the end.

Following on with our previous example where we have the file "welcome" that has the contents of "hey". If were to use echo to add "hello" to the file using the `>` operator, the file will now only have "hello" and not "hey".



# Reading files
for special characters we use
```bash
cat ./-
```
`./` signifies that its in the current directory

for spaces in filename you just indicate the spaces like `\ ` or put the entire file name with spaces in quotes

### file
```bash
file filename
```
returns the file type


Over the wire bandit7 
ssh -p 2220 bandit7@bandit.labs.overthewire.org z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

for deleting a directory
```bash
rm -R directory
```

# Permissions
`su user` is used to switch between users


level 9 password EN632PlfYiZbn3PhVK3XOGSlNInNE00t
level 12 password JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
level 14 password fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
