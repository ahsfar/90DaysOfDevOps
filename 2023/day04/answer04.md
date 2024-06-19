## Explain in your own words and examples, what is Shell Scripting for DevOps.
Shell is a program in linux which performs task given by user. And scripting is basically series of these commands can be added to a shell scripting file and users can run so it makes life esier to not run commands one by one. We can use this script in automation pieplien to auotamte thigns a sereis of command basically. 
e.g. running of userdata after ec2 provision to setup the environment

## What is #!/bin/bash? can we write #!/bin/sh as well?
Shbang it's written in the begining of the scripting file it tells linux thath it's a script /bash and /sh or two differnt shell programs both can be used it just tells the linux which one to use.

## Write a Shell Script which prints I will complete #90DaysOofDevOps challenge
#!/bin/bash

echo "I will complete #90DaysOfDevOps challenge"

## Write a Shell Script to take user input, input from arguments and print the variables.
#!/bin/bash

echo "testing"

echo -n "Please enter your name?"

read name

echo  "Welcome" $name

## Write an Example of If else in Shell Scripting by comparing 2 numbers

#!/bin/bash
echo "testing"
echo -n "Please enter your name?"
read name
echo  "Welcome" $name
echo -n "Please enter a number above 10"
read num
compare=10
if [ $num -gt $compare ]
then
    echo "You entered the correct number"
else
    echo "You entered number less than 10"
fi
