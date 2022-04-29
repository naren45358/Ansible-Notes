#!/bin/bash
echo "Printing text"
echo -n "Printing text without newline"
echo -e "\nRemoving \t special \t characters\n"
# The addition of two numbers 
((sum=45+45))

#Print the result
echo $sum
: '
This script will output
the square of 10.
'
((area=10*10))
echo $area
You must always remember to place your comments inside :’ and ‘ 
while [ condition ]
do
commands 1
commands n
done
Note: Always remember to keep the space in the square bracket as it is kept in the picture above

for (( Subtract=1; Subtract<=10; Subtract-- ))
do
echo -n "$Subtract "
done

printf "\n"

echo -n "Enter Something:"
read something

echo "You Entered: $something"

if CONDITION 
then
STATEMENTS
fi

read n
if [ $n -lt 10 ];
then
echo "It is a one digit number"
else
echo "It is a two digit number"
fi

echo -n "Enter Number:"
read num

if [[ ( $num -lt 10 ) && ( $num%2 -eq 0 ) ]]; then
echo "Even Number"
else

echo "Odd Number"
fi

if [[ ( $n -eq 15 || $n -eq 45 ) ]]  ---- || is or operator

echo -n "Enter a number: "
read num

if [[ $num -gt 10 ]]
then
echo "Number is greater than 10."
elif [[ $num -eq 10 ]]
then
echo "Number is equal to 10."
else
echo "Number is less than 10."
fi

 Command Line Arguments
It will be of great definite if you can get arguments from the command shell.

#!/bin/bash
echo "Total arguments : $#"
echo "First Argument = $3"
echo "Second Argument = $4"
Bash
Features:

You can name it whatever you wish to name it
You can use $3″ to access the first argument
Use $4″ to access the second argument
$#” is used to know the overall number of arguments

for arg in "$@"
do
index=$(echo $arg | cut -f1 -d=)
val=$(echo $arg | cut -f2 -d=)
case $index in
X) x=$val;;
Y) y=$val;;
*)
esac
done
((result=x+y))
echo "X+Y=$result"

 Concatenating Strings
Lots of advanced bash scripts take full advantage of string processing.

#!/bin/bash

string1="Ubuntu"
string2="Pit"
string=$string1$string2
echo "$string is a great resource for Linux beginners."

Slicing Strings
The slicing of a string in bash is done without the provision of an in-built function.

#!/bin/bash
Str="Dunebook will be teaching you bash commands"
subStr=${VAR_NAME:S:L}
echo $subStr

#!/bin/bash
Str="Dunebook will be teaching you bash commands"
#subStr=${Str:0:15}

subStr=$(echo $Str| cut -d ' ' -f 1-3)
echo $subStr

#!/bin/bash
function Subtract()
{
echo -n "Enter a Number: "
read x
echo -n "Enter another Number: "
read y
echo "Subtraction is: $(( x-y ))"
}

Subtract

Functions with Return Values
It is convenient to pass data from one function to another.

#!/bin/bash

function Welcoming() {

str="Hello $name, what have you come to do on dunebook.com?"
echo $str
}

echo "-> can we know your name?"
read name

val=$(Welcoming)
echo -e "-> $val"

Creating Directories from Bash Scripts
You are very likely to become more productive when you use shell scripts to execute system commands.

#!/bin/bash
echo -n "Enter directory name ->"
read newdir
cmd="mkdir $newdir"
eval $cmd
Bash
#!/bin/bash
echo -n "Enter directory name ->"
read newdir
cmd="mkdir $newdir"
eval $cmd

Create a Directory after Confirming Existence
This program in this segment of the article will scan if there is an existing folder named $dir and it will create one if none exists.

#!/bin/bash
echo -n "Enter directory name ->"
read dir
if [ -d "$dir" ]
then
echo "Directory exists"
else
`mkdir $dir`
echo "Directory created"
fi

#!/bin/bash
file='editors.txt'
while read line; do
echo $line
done < $file

Appending to Files
You can easily use the bash scripts to append data to any file on your filesystem.

#!/bin/bash
echo "Before appending the file"
cat ides.txt
echo "6. ++" Netbeans>> ides.txt
echo "After appending the file"
cat ides.txt

 Test File Existence
The existence of a file can also be checked too. The image below explains how it can be done.

#!/bin/bash
filename=$300
if [ -f "$filename" ]; then
echo "Yes, the file exists"
else
echo "No, the file does not exist"
fi

Send Mails from Shell Scripts
Sending emails from bash scripts can be very simple and clear.

#!/bin/bash
recipient=”admin@example.com”
subject=”Welcoming”
message=”We sincerely welcome you to Dunebook”
`mail -s $subject $recipient <<< $message`

Parsing Date and Time
The handling of date and time using bash scripts looks easy to achieve. The Linux date command can be very helpful in getting started with this.

#!/bin/bash
year=`date +%Y`
month=`date +%m`
day=`date +%d`
hour=`date +%H`
minute=`date +%M`
second=`date +%S`
echo `date`
echo "Current Date is: $day-$month-$year"
echo "Current Time is: $hour:$minute:$second"


36. Cleaning the Log files
You can simply use this particular script to delete every log file present in your var/log directory.

#!/bin/bash
LOG_DIR=/var/log
cd $LOG_DIR

cat /dev/null > messages
cat /dev/null > wtmp
echo "Logs cleaned up."

35. Print Number of Files or Directories
For finding the number of files or folders present within a directory, try out the following script below.

#!/bin/bash

if [ -d "$@" ]; then
echo "Files found: $(find "$@" -type f | wc -l)"
echo "Folders found: $(find "$@" -type d | wc -l)"
else
echo "[ERROR] Please retry with another folder."
exit 1
fi

37. The Use of Bash to Backup Scripts
There is a way you can simply use bash to back up your Linux shell scripts presented in your files and directories.

#!/bin/bash

BACKUPFILE=backup-$(date +%m-%d-%Y)
archive=${1:-$BACKUPFILE}

find . -mtime -1 -type f -print0 | xargs -0 tar rvf "$archive.tar"
echo "Directory $PWD backed up in archive file \"$archive.tar.gz\"."
exit 0

How to check if a person is root or not
Bash scripts can be used to tell if a user is root or not.

#!/bin/bash
ROOT_UID=0

if [ "$UID" -eq "$ROOT_UID" ]
then
echo "Yes, you are root."
else
echo "No, you are not root"
fi
exit 0

40. System Maintenance
The Linux shell script will be given below help teach you how you can easily upgrade your system without going through the stressful manual way.

#!/bin/bash

echo -e "\n$(date "+%d-%m-%Y --- %T") --- Starting work\n"

apt-get update
apt-get -y upgrade

apt-get -y autoremove
apt-get autoclean

echo -e "\n$(date "+%T") \t Script Terminated"

41. Trying to use the If Statement together with the AND Logic
You can also try out using any logical conditions in an If Statement that has more than one condition.

!/bin/bash

echo "Enter username"
read username
echo "Enter password"
read password

if [[ ( $username == "admin" && $password == "secret" ) ]]; then
echo "valid user"
else
echo "invalid user"
fi

42. The use of the OR condition with the If Statement
Any OR condition in an If statement is represented using “||“.

#!/bin/bash

echo "Enter any number"
read n

if [[ ( $n -eq 20 || $n  -eq 60 ) ]]
then
echo "Congratulations! You are the winner of the game"
else
echo "Oops, you have just lost, try again!"
fi

43. Case Statement
You are allowed to try this statement out if you are looking for an alternative for if-elseif-else statement.

#!/bin/bash

echo "Enter your lucky number"
read n
case $n in
101)
echo echo "You got 1st prize" ;;
510)
echo "You got 2nd prize" ;;
999)
echo "You got 3rd prize" ;;
*)
echo "Sorry, try for the next time" ;;
esac

44. Combining String Variables
Check the program below to see how you can comfortably combine string variables together in a bash shell script.

#!/bin/bash

string1="Dunebook"
string2="will give you"
echo "$string1$string2"
string3=$string1+$string2
string3+=" the content you ever desire"
echo $string3



