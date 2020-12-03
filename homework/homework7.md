# Homework 7: Cloud Automation Part 2
Copyright (C) 2020 Thomas Underhill.  All Rights Reserved.

This homework is optional for extra credit, but you may need the information provided in this homework to complete your project.  If you choose to submit for extra credit, please use the "Extra Credit HW7" box that is located in Cougar Courses under Module 15.

## Prerequisites

You must complete all other homework assignments and all modules up through and including Module 8 before starting this assignment.

You must have Terraform installed on your Linux system.  If you do not, then go back to earlier modules and install Terraform following the instructions for your version of Linux.

You must have Git installed on your Linux system and configured for your GitHub account.  If you do not, then go back to earlier modules and install/configure Git.

You must be confident in using Git, GitHub, and Terraform.  If NOT, then go back and practice some more.

## Objective
Upon the completion of this assignment, you should be able to use Terraform to provision network and compute infrastructure in GCP.  

## Instructions
**You must use GCP for Homework 7 due to AWS Educate limitations.  You will NOT be able to use AWS for this assignment.**

If you have not gone through the Terraform Tutorial exercise in the Module 6 instructions, then STOP NOW!  You need to complete that exercise first.

If you have not setup GitHub yet in Homework 5, then STOP NOW!  You need to complete Homework 5 first.

1. Login to your Linux instance through SSH (if you have multiple instances, whichever one has Terraform and GitHub setup on it is fine.  If you have multiple installs of Terraform and GitHub then just pick one to use.).
2. Change to your local Git directory (in my example, this is called "mygit" without the quotes, but the name is whatever you named yours)
```
cd ~/mygit
```
3. Change to your Homework repository (in my example, this is called "Your_Name_Homework", but yours will be whatever you named it).
```
cd Your_Name_Homework
```
4. Create a directory in your local copy of the Homework repository for Terraform.
```
mkdir terraform
```
5. Change to the terraform directory that you just created.
```
cd terraform
```
6. Create an empty main.tf file in the terraform directory.
```
touch main.tf
```
6. Add the empty main.tf file to GitHub.
```
git add main.tf
```
Note: to add multiple files simultaneously, you may use ```git add FILE1 FILE2 FILE3``` or ```git add .```
7. If you wish to set vi/vim as the default editor, make sure to type:
```
set -o vi
```
If you wish to use Nano, then you do not need to do this step.
8. Commit the empty main.tf file to GitHub.  Enter a comment when prompted using your text editor.  Save your edits using the mechanism provided by your text editor (i.e. ```:wq! on vim``` )<br>
```
git commit -a
```
9. Push your changes to GitHub.
```
git push
```
10. Verify that your changes pushed to GitHub by visiting your repository in your web browser.  i.e. https://github.com/yourgithubname
11. Go through the Terraform GCP tutorial to set up your main.tf and other files.  If Terraform is not installed on your Linux instance, follow the instructions for the appropriate Linux distribution.  DO NOT INSTALL DOCKER, IT IS NOT NEEDED!
12. Create a GCP Service Account Key
https://console.cloud.google.com/apis/credentials/serviceaccountkey
When creating the key, use the following settings:

Select the project that you created for this class.
Under "Service account", select "New service account".
Give it any name you like.
For the Role, choose "Project -> Editor".
Leave the "Key Type" as JSON.
Click "Create" to create the key and save the key file to your system.
You can read more about service account keys in Google's documentation.<br>
13. Add a rule to exclude the JSON file created in the previous step to a .gitignore file at the root level of your Git repository.  In my example this is ~/mygit/Your_Name_Homework/.gitignore
and my JSON file was named mis484-6.json

My .gitignore would contain:
*.json

14. Commit your changes to Git
Commit all of the files to GitHub. Enter a comment when prompted using your text editor. Save your edits using the mechanism provided by your text editor (i.e. :wq! on vim )
git commit -a

Push your changes to GitHub.
git push

Verify that your changes pushed to GitHub by visiting your repository in your web browser. i.e. https://github.com/yourgithubname



You will document your progress in a brief report that meets the requirements below:
<ul>
  <li>MS Word or PDF document
  <li>12-point font
  <li>Single-spaced
  <li>You must include a screenshot of each step in this assignment
  <li>Minimum of 500 words
  <li>Organized using an Introduction, Reflection, and Conclusion style
  <li>Your reflection will be a discussion of your progress as you complete the homework, including describing any challenges, how you overcame any challenges, and what you learned on this assignment.
</ul>
