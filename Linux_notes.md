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

