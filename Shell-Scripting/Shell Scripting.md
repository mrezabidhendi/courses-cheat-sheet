- Provide the default shell path after the shebang (`#!`) sign.
```sh
# to get the current shell path :
echo $SHELL
// output : /bin/bash
```

```sh
#!/bin/bash
echo Hello World!
```
- Change the shell file to executable by using `chmod` command:
```sh
chmod u+x helloworld.sh
```
- This an example of a `.sh` file. It shows the usage of *variables* and `read` command.
```sh
#!/bin/bash
echo What is your name?
read First_Name
echo What is your last name?
read Last_Name
echo Hello $First_Name $Last_Name
```
- Positional arguments are variables used in bash files that consist of numbers. The number points to the place of the arguments passed along while running the script in the shell, example:
```sh
./script.sh Mohamad 1996
// output : Hello Mohamad you were born in 1996

# ./script.sh file:
echo Hello $1 you were born in $2
```
- Usage of command-line operators:
```sh
#PIPE |
#greater than >
// Write to File
#double greater than >>
// APPEND TO FILE
#lesser than <
// pass contents of a file to a command
#double lesser than <<
// get input from commandline and end it when the word passed after the sign is repeated again.
#example :
wc -w << endf
hello
how's it going?
endf
#triple lesser than <<<
// pass the string that came after the sign to the command before the sign
```
- Test Expressions
```sh
[ text1=text2 ]
[ 1=0 ]
[ 1 -eq 1 ] // ONLY FOR NUMBERS
```
- Some useful commands:
```sh
${1,,} // CONVERTING THE FIRST ARGUMENT PASSED TO THE SCRIPT TO lowercase
${1^^} // CONVERTING THE FIRST ARGUMENT PASSED TO THE SCRIPT TO UPPERCASE
$? // RETURNS THE RETURN STATE OF THE LAST COMMAND. 0 IF EVERYTHING OKAY
```
- if / elif /else statements
```sh
#!/bin/bash
if [ ${1,,} = mohamadreza ] ; then
	echo 'You are the Owner of this CoMpUtEr'
elif [ ${1,,} = help ] ; then
	echo "Who's the owner of this PC?"
else
	echo who art tho
fi  // to end conditional blocks
```
- case statement
```sh
#!/bin/bash
case ${1,,} in
	mohamadreza | administrator)
		echo 'You are the Owner of this CoMpUtEr'
		;;
	
	help)
		echo "Who's the owner of this PC?"
		;;
	*)
		echo who art thou
		;;
esac // to end case blocks
```
- 