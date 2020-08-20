# Homework #2: Getting Started with the Linux Command Line

## Prerequisites
In order to complete this assignment, you must already have your Google Cloud Platform and Amazon Web Services accounts setup.  If you haven't done this yet, refer to the instructions located in Cougar Courses.  

You must also complete Homework #1 before starting this assignment.

## Objective
Upon the completion of this assignment, you should be able to perform common Linux command line (CLI) activities and have confidence in using the CLI.

## Instructions
You will use either your GCP or AWS virtual machine from Homework #1 to perform the tasks in this lab.  It doesn't matter which one you use.  To receive full credit, you must complete all parts of this assignment.  

You will document your progress in a brief report that meets the requirements below:
<ul>
  <li>MS Word or PDF document
  <li>12-point font
  <li>Single-spaced
  <li>You must include a screenshot of each step in this assignment
  <li>Minimum of 250 words
  <li>Organized using an Introduction, Reflection, and Conclusion style
  <li>Your reflection will be a discussion of your progress as you complete the homework, including describing any challenges, how you overcame any challenges, and what you learned on this assignment.
</ul>

###### Please be sure to review the explanatory, "walk-through" videos on my YouTube channel as well as the optional supplemental materials under Module 2 in Cougar Courses.

## Part 1: Basics
1.	Login to your virtual machine using SSH - you should use the web browser based SSH client in the cloud provider's web UI, unless you already have a local SSH client setup and understand how to configure your SSH keys.
2.	Output the location of the directory that you are in upon logging in using ```pwd```
3.	Output your username using ```whoami```
4.	Output the hostname using ```uname -n```
5.	Output a list of all users currently logged into your virtual machine using ```who```

  Note: you can also use the ```w``` command to output a list of users and their current activities.

6.	Output the uptime of your virtual machine with ```uptime```

## Part 2: Navigation and File Management
1.	Create a new directory with your first initial and last name using the ```mkdir``` command.  For example, ```mkdir jdoe```.
2.	Change to the directory that you just created using the ```cd``` command.  For example, ```cd jdoe```.
3.	Use a simple for loop to create numbered files in the directory from the previous step.

  Enter each line of the formatted text and hit ENTER after each line.  
```
for NUM in `seq 1 99`
do
touch file${NUM}.txt
done
```

  This example uses the ```seq``` command inside of a ```for loop``` with a variable ```NUM``` set to the output of the ```seq``` command to generate a range of numbers between 1 and 99.  The value of ```NUM``` is set to append a filename created using the ```touch``` command and then the process repeats until the ```for loop``` completes running through the sequence of numbers.  
4.	List all files (including hidden files) in the current directory using the ```ls -a``` command.
5.	Count all files in the current directory by piping the output of the ```ls``` command to the ```wc``` command with ```ls -a | wc -l```
6.	List all files in the current directory and output to a text file using something like this (``ls -al >listfiles``)
7.	Concatenate the file from the previous step using the ```cat``` command.
8.	Rename all of the text files in the current directory using a simple for loop like this.

    Enter each line of the formatted text and hit ENTER after each line.
```
for FILE in `ls *.txt`
do
mv $FILE new$FILE
done
```

  This example uses the ```ls``` command inside of a ```for loop``` with a variable ```FILE``` set to the output of the ```ls``` command to generate a list of files.  The value of ```FILE``` is used twice in the ```mv``` command - first as the original filename and then appended to ```new``` to generate a new filename.  The ```mv``` command renames the file.  This process repeats until the ```for loop``` completes running through the list of files.
9.	Change to your home directory using ```cd ~```
10.	Change to the /etc directory and count the number of files ```cd /etc;ls -a | wc -l```

## Part 3: File Editing
You may use either the vim or nano editor to perform these tasks.  This is a matter of personal preference.  The instructions for ```vim``` are prefaced with ****vim:**** and the instructions for ```nano``` are prefaced with ****nano:****.  

As a CSUSM student, you have access to the [O'Reilly Safari reference book library](https://biblio.csusm.edu/content/safari-books).  I recommend that you utilize the [vim](https://learning.oreilly.com/library/view/learning-the-vi/9781492078791/) books available through this library to help you learn how to use vim.  You might also wish to review the [beginner's explanation of vim modes](https://www.freecodecamp.org/news/vim-editor-modes-explained/).  If nano is more your cup of tea, then you can review the [nano beginner's guide](https://www.howtogeek.com/howto/42980/the-beginners-guide-to-nano-the-linux-command-line-text-editor/) or this [introduction to nano resource](https://staffwww.fullcoll.edu/sedwards/Nano/IntroToNano.html).

1.  Create a new file in your home directory using your text editor called ```homework2```.
3.  Type or copy and paste the following text into the above file:
  ```This is a story about a dog named Clyde, a cat named Flyde, and parrot named Plyde.  One morning Clyde went to visit Flyde for breakfast, but when he arrived, Flyde was gone and Plyde had taken his place.  Clyde asked Plyde "where is Flyde?" and Plyde replied that Flyde had gone to visit a human named Hyde.  Well, Clyde thanked Plyde and went on his way to find Flyde at Hyde's house.  When Clyde arrived at Hyde's house, he found Flyde sitting outside.  Flyde and Hyde invited Clyde inside and they all laughed at Clyde's adventure.```
4. Save the file.  
  ****vim****: You will use the ```ESC``` key and then type ```:w!```.  <br>
  ****nano****: You will use the ```Ctrl``` key and then press the letter ```O``` key.<br>
5. Find all instances of "lyde" and replace with "oyd".  <br><br>
****vim****: <br>
  you will use the ```ESC``` key and then type ```:%s/lyde/oyd/g```  <br><br>
  What does this mean? Let's break this down: <br>
```ESC``` changes ```vim``` modes. <br>
```:``` enables you to enter a vim command.<br>
```%s```stands for substitute. <br>
```/lyde``` is your search parameter. <br>
```/oyd``` is your replacement text. <br>
```/g``` indicates that you wish to replace the text globally throughout the document.

  ****nano****: <br>
  You will use the ```Ctrl``` key and then press the ```\``` key, enter your *search string*, use the ```RETURN``` key, enter your *replacement string*, use the ```RETURN``` key, and then press the letter ```A``` key to replace all instances.<br>  
6. Take a screenshot of the edited file and explain how this global find/replace saved you time versus manually changing each instance of the name.  All of the instances of ```lyde``` are now ```oyd``` - ```Flyde``` is now ```Floyd```, ```Clyde``` is now ```Cloyd```, ```Plyde``` is now ```Ployd```, and ```Hyde``` is now ```Hoyd```.
7. Quit your text editor.  In ```vim```, you will use the ```ESC``` key and then type ```:wq!```.  In ```nano```, you will use ```Ctrl``` and then press the letter ```X``` key.  You will then press the letter ```Y``` key when prompted to save your changes.

## Part 4: Process Management and Input/Output

1.  Check to see which processes are running and resource (CPU/Memory/Network) utilization using the  ```top``` command.
2.  What are the values for Load Avg. on your VM?
3.  How many processes does your system report?  How many are running versus sleeping?
4. Which process has the highest %CPU value?  Is this consistent or does it change?  What do you think causes this behavior?
5.  Type the letter ```q``` to close the ```top``` command.  
6.  Use the ```grep``` command with the ```ps``` command to search for the ```bash``` command.  You'll need to use the pipe (```|```) to link the output of the ```ps``` command to the input of the ```grep``` command.  <br>
Example: ```ps -ef | grep bash```
7.  Exclude the ```bash``` command from the output of the ```ps``` (Process Show) command using a pipe (```|```) and the ```grep``` command to filter output out.  <br>
Example: ```ps -ef | grep -v bash```
8.  Redirect output from the screen to a file using the redirection ```>``` symbol with a command. <br> Example: ```ls -al / >/tmp/ls.log```
9.  View the contents of the log file from the previous step.  <br>
Example: ```cat /tmp/ls.log```
10. Use the contents of a file as input to another command.  <br>
Example: ```wc -l </tmp/ls.log``` <br><br>
This example does a word count for the number of lines in the input file (/tmp/ls.log).  Another way of doing without redirecting the input would be to pipe the output of the `cat` command to `wc` like this ```cat /tmp/ls.log | wc -l```


## Part 5: Package Management
Package management is Linux distribution dependent.  RedHat-based family of distributions, such as Amazon Linux, CentOS, Fedora, or RedHat use the *RPM* package format and *yum* to manage packages.  Debian-based family distributions, such as Debian or Ubuntu use the *DEB* package format and *apt* to manage packages.  <br>

As such, there are two possible paths for you to follow.  I will provide instructions for both paths, but you only need to complete one of the paths for each step.  I will use the abbreviations *RedHat* and *Debian* in the instructions below, but the instructions should work on any of the distributions within a particular family.
<br>
1.  Ensure that your Linux VM has the latest versions of packages installed.  Note that the [```sudo``` command](https://www.linux.com/training-tutorials/linux-101-introduction-sudo/) is used to temporarily run a command as a privileged (super) user.  If you happen to be connected to your VM as the root user (*strongly discouraged* as a horrible habit), then you may omit the ```sudo``` portion below.

  ****RedHat:****  <br>
  ```sudo yum upgrade``` <br> <br>
  ****Debian:****  <br>
  ```sudo apt-get upgrade``` <br>
2.  Install the ```nginx``` web server package. <br><br>
  ****RedHat:**** <br>
  ```sudo yum install epel-release``` will install the EPEL repository. <br>
  ```sudo yum update``` will update the repository.<br>
  ```sudo yum install nginx``` will install NGINX.<br>
  ```sudo nginx -v``` will verify the installation of NGINX.<br>

  ****Debian:****  <br>
  ```sudo apt-get update``` will update the Debian repository. <br>
  ```sudo apt-get install nginx``` will install NGINX. <br>
  ```sudo nginx -v``` will verify the installation of NGINX. <br>
3.  Install the ```GNU Screen``` package.
<br><br>
  ****RedHat:**** <br>
  ```sudo yum install screen```
  <br><br>
  ****Debian:**** <br>
  ```sudo apt-get install screen```
