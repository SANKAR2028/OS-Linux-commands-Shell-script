```
NAME: SANKAR S
DEPT: CSE
REG NO: 212224040291
```
# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
^d
```
## OUTPUT
![alt text](1.png)

cat > file2
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta

```
## OUTPUT
![alt text](2.png)
### Display the content of the files
cat < file1
## OUTPUT
![alt text](3.png)

cat < file2
## OUTPUT
![alt text](4.png)

# Comparing Files
cmp file1 file2
## OUTPUT
 ![alt text](5.png)

 
diff file1 file2
## OUTPUT
![alt text](7.png)

#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
## OUTPUT
![alt text](8.png)
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```
## OUTPUT
![alt text](9.png)

cut -c1-3 file11
## OUTPUT


![alt text](10.png)

cut -d "|" -f 1 file22
## OUTPUT
![alt text](11.png)


cut -d "|" -f 2 file22
## OUTPUT
![alt text](12.png)

cat > newfile 
```
Hello world
hello world
^d
```
## OUTPUT
![alt text](13.png)


14.grep Hello newfile 
## OUTPUT
![alt text](14.png)



15.grep -v hello newfile 
## OUTPUT
![alt text](15.png)


16.cat newfile | grep -i "hello"
## OUTPUT

![alt text](16.png)


17.cat newfile | grep -i -c "hello"
## OUTPUT

![alt text](17.png)


grep -R ubuntu /etc
## OUTPUT

![alt text](18.png)

grep -w -n world newfile   
## OUTPUT
![alt text](19.png)

cat > newfile 12
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```
## OUTPUT
![alt text](20.png)

cat < newfile12
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
## OUTPUT
![alt text](21.png)
egrep -w 'Hello|hello' newfile 
## OUTPUT

![alt text](22.png)

egrep -w '(H|h)ello' newfile 
## OUTPUT
![alt text](23.png)


egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT

![alt text](24.png)


egrep '(^hello)' newfile 
## OUTPUT

![alt text](25.png)

egrep '(world$)' newfile 
## OUTPUT

![alt text](26.png)

egrep '((W|w)orld$)' newfile 
## OUTPUT
![alt text](27.png)

egrep l{2} newfile
## OUTPUT


egrep 's{1,2}' newfile
## OUTPUT

![alt text](28.png)

cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```
## OUTPUT 
![alt text](29.png)
cat < file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```
## OUTPUT
![alt text](30.png)
sed  -e 's/Ram/Sita/' file23
## OUTPUT
![alt text](31.png)

sed  -e '2s/Ram/Sita/' file23
## OUTPUT
![alt text](32.png)

sed -n -e '2,/Joe/p' file23
## OUTPUT

![alt text](35.png)


sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
![alt text](36.png)



seq 10 
## OUTPUT

![alt text](37.png)

seq 10 | sed -n '4,6p'
## OUTPUT

![alt text](38.png)

seq 10 | sed -n '2,~4p'
## OUTPUT
![alt text](39.png)


seq 3 | sed '2a hello'
## OUTPUT

![alt text](40.png)

seq 2 | sed '2i hello'
## OUTPUT
![alt text](41.png)

seq 10 | sed '2,9c hello'
## OUTPUT
![alt text](42.png)
sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
![alt text](43.png)



#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
## OUTPUT
![alt text](45.png)
sort file21
## OUTPUT
![alt text](46.png)

cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
## OUTPUT
![alt text](47.png)
uniq file22
## OUTPUT

![alt text](48.png)

#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
![alt text](49.png)
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
 ## OUTPUT
![alt text](50.png)

cat urllist.txt | tr -d ' '
 ## OUTPUT
![alt text](51.png)

 
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT

![alt text](52.png)

cat > scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```
## OUTPUT
![alt text](53.png)
cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
## OUTPUT
 ![alt text](54.png)



 
ls file1
## OUTPUT
![alt text](55.png)
echo $?
## OUTPUT 
![alt text](56.png)
 
# mis-using string comparisons

cat > strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```
## OUTPUT
![alt text](57.png)
cat < strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```

## OUTPUT
![alt text](58.png)

# check file ownership
cat > psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```
## OUTPUT
![alt text](59.png)
cat < psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```

## OUTPUT
![alt text](60.png)

# looking for a possible value using elif
cat > elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```
## OUTPUT


![alt text](67.png)
# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
## OUTPUT
![alt text](68.png)
# using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
## OUTPUT
![alt text](69.png)
cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
## OUTPUT
![alt text](70.png)
cat > untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
## OUTPUT

 ![alt text](71.png)
 
 
cat > forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 ## OUTPUT
![alt text](72.png)
 
cat > forin2.sh 
``` bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
## OUTPUT
![alt text](73.png)
cat > forin3.sh 
```
bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
## OUTPUT 
![alt text](74.png)
cat > forin1.sh 
```
bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
## OUTPUT
![alt text](75.png)
cat > forinfile.sh 
```
`bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
## OUTPUT
![alt text](76.png)

cat> forctype.sh 
```
bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
```
## OUTPUT
![alt text](77.png)
cat > fornested1.sh 
```
bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```
 ## OUTPUT
![alt text](78.png)
 
cat > forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```
## OUTPUT
![alt text](79.png)
cat< forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```

## OUTPUT
 ![alt text](80.png)
cat >exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```

## OUTPUT
![alt text](81.png)

 cat< exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
 

## OUTPUT

![alt text](82.png)


 
cat >funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
## OUTPUT

![alt text](83.png)
 
cat> argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```

## OUTPUT
![alt text](84.png)
 
 cat < argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
## OUTPUT
![alt text](85.png)
 
 
cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
## OUTPUT
![alt text](86.png)


cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```
## OUTPUT 
![alt text](87.png)

awk -f nc.awk data.dat

## OUTPUT 
 ![alt text](88.png)
cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
## OUTPUT 
![alt text](89.png)

# RESULT:
The Commands are executed successfully.
