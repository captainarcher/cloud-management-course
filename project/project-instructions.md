# Project Instructions
Copyright (C) 2020 Thomas Underhill.  All Rights Reserved.
<br>

## General instructions
This project is designed to give you a practical business problem to solve using what you have learned in this course.  This immersive learning activity will prepare you for a career in the MIS field and you are encouraged to use this as an example for your portfolio.  You will need to conduct analysis of the business problem, perform independent Internet research to see how similar problems have been solved by others, and then complete five different types of assignments.  These assignments range from an executive level presentation of a proposed solution, an architecture drawing of the proposed solution, and then three technical implementations (automation, infrastructure, and security).  

There will be discretionary extra credit available for exceptional work on this project.  If you go above and beyond what is expected, then you may receive extra credit points at my discretion.

## Submission Instructions
In addition to submitting to the box under Module 15 in Cougar Courses, all Terraform and Vault configurations need to be committed to your private GitHub project repository (Your_Name_MIS484-6_Project) that you shared with Professor Underhill in Homework #5.  DO NOT use a Public GitHub repository!

Your final project submission must include: PowerPoint slides, link to your elevator pitch video, architecture drawing, github repository access with Terraform and Vault files, and three reflection papers.  You are encouraged to zip all of these files up prior to submission.

## Hypothetical
CougarFlix is the largest video streaming service for college-aged students.  The company currently runs its own IT infrastructure in a Mira Mesa data center and a disaster recovery facility in Virginia.  The company’s video production facilities are in a large skyscraper in downtown San Marcos, which has been closed due to COVID-19.  After seeing the success of the Saturday Night Live @ Home series, the company has decided to move all production to the homes of employees.  This poses a problem, because the existing IT infrastructure is not adequate for a distributed workforce let alone video production and distribution.  Your manager, the VP of IT, has asked that you put together a proposal for the company to shift all IT infrastructure to cloud-based providers.  You should consider costs, supportability, availability, reliability, and scalability as part of your proposal.  Your proposal will consist of 5-7 slides and a 1-minute “elevator pitch” video that highlights the advantages and disadvantages of cloud adoption.  To counteract the disadvantages, you should discuss how your proposal mitigates any disadvantages.  In addition, you will design and implement a pilot cloud deployment for the organization’s corporate website using common automation and security software discussed in this course.  You may not simply propose using a SaaS (Software as a Service)-based service like WordPress.com, Wix, or Squarespace.  You must propose using either Amazon Web Services (AWS) or Google Cloud Platform (GCP) as an Infrastructure as a Service (IaaS) platform for this project.   <br>

## Executive Presentation (20% of your project grade - 7 points)
You will create an executive presentation slide deck in PowerPoint format (5-7 slides) and separately record a 1-minute “elevator pitch” video (YouTube or Vimeo) pitching your proposed Cloud Adoption plan to executive leadership.

Your cloud adoption plan should address the hypothetical scenario earlier.  

Videos exceeding 1-minute or under 1-minute will be penalized as follows:
<li>Less than 30 seconds (No credit)
<li>31-40 seconds (-75% penalty)
<li>41-50 seconds (-50% penalty)
<li>51-60 seconds (No penalty)
<li>61-70 seconds (No penalty)
<li>71-90 seconds (-25% penalty)
<li>91-120 seconds (-50% penalty)
<li>121-180 seconds (-75% penalty)
<li>Greater than 181 seconds (No credit)

## Cloud Architecture Design Drawing (20% of your project grade - 7 points)
You will use use [LucidChart](https://www.lucidchart.com/pages/usecase/education) (free for students) or [CloudCraft.co](CloudCraft.co) (free plan) to create an architecture design drawing for the organization's website infrastructure.  It doesn't matter what you use for the website, but one approach would be to use the self-hosted version of WordPress from WordPress.org in either GCP or AWS.  There are examples of Architecture drawings in Module 5.

A sample architecture for the self-hosted WordPress in AWS might include: <br>
<li>Amazon Relational Database Service (RDS) or an EC2 instance running a database such as MySQL or MariaDB
<li>Amazon S3 Object Storage
<li>Amazon Virtual Private Cloud (VPC) to segment networks into Internet accessible, internal only, and highly-restricted
<li>Amazon EC2 Virtual Machines running WordPress
<li>Amazon Elastic Load Balancers in front of the web servers running a web server such as nginx or Apache and WordPress<br><br>

A sample architecture for the self-hosted WordPress in GCP might include: <br>
<li>GCP Compute instance running MySQL or MariaDB databases
<li>GCP Compute instances (VMs or Containers) running a web server such as nginx or Apache and WordPress
<li>Network segmentation into Internet accessible, internal only, and highly-restricted
<li>Load balancers

You are not limited to the above examples.  Points are awarded for creative solutions that would meet the stated requirements.
## Cloud Automation Deployment (20% of your project grade - 7 points)
After you have completed designing your cloud architecture, you will use Terraform to manage the deployment of cloud infrastructure.

You need to create the infrastructure for your cloud deployment using Terraform.  Whether you use GCP, AWS, or a mixture of the two is entirely up to you.

Make sure to check your Terraform files into your private GitHub project repository that you created in Homework #5.  Anytime that you edit your Terraform files, push the changes into GitHub.  This will enable you to revert any changes that break Terraform.

You should use Terraform Plan to test changes before doing a Terraform Apply.

Your deliverables for this portion of the assignment will be:<br>
<li>Copies of all Terraform files in your GitHub Repository
<li>Successful Terraform Apply (be sure to capture your screen after the apply or output to a log file and include that in your paper
<li>Reflection Paper that includes the following: screenshots or text from logged successful Terraform Apply commands and brief narrative (500 words) of what you accomplished along with how you overcame any challenges during this portion of the project.<br>

## Cloud Infrastructure Deployment (20% of your project grade - 7 points)
Upon completion of the automation portion of this assignment use Terraform Show and the Cloud Console to capture a picture of what your cloud infrastructure looks like.  Write a brief narrative (500 words) that describes all of your infrastructure, along with your reasoning for choosing that infrastructure, and be sure to either include the output of terraform show and screenshots from your cloud console.<br>

## Cloud Security Deployment (20% of your project grade - 7 points)
You will deploy Vault to either GCP or AWS and use it to store and manage credentials.  The basic requirement to get a grade for this portion is to be able to create sample credentials in Vault.

You should include your Vault configuration files in your GitHub private project repository.

You will also write a reflection paper of 500 words that explains how you would implement Vault in a real-world scenario to manage credentials.  You should talk about your own implementation as well.  Your paper needs to have screenshots of the work that you're doing in Vault.

Optionally, you may wish to manage credentials using the tools/plugins below for extra credit:

[Vault Plugin for MySQL/MariaDB](https://www.vaultproject.io/docs/secrets/databases/mysql-maria)<br>
[Vault Plugin for WordPress](https://github.com/humanmade/hashicorp-vault)<br>
[Vault Google Cloud Auth](https://www.vaultproject.io/docs/auth/gcp.html)<br>
[Vault AWS Secrets](https://learn.hashicorp.com/tutorials/terraform/secrets-vault)<br>
