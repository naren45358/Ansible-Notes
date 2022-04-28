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
