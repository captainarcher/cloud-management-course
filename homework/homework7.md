# Homework 7: Cloud Automation Part 2
Copyright (C) 2020 Thomas Underhill.  All Rights Reserved.

****This assignment is not ready for students - PLEASE CHECK BACK ON or AFTER 11/21****

## Prerequisites

You must complete all other homework assignments and all modules up through and including Module 8 before starting this assignment.

You must have Terraform installed on your Linux system.  

You must have Git installed on your Linux system and configured for your GitHub account.

You must be confident in using Git, GitHub, and Terraform.  If NOT, then go back and practice some more.

## Objective
Upon the completion of this assignment, you should be able to use Terraform to provision network and compute infrastructure in GCP.  Your GCP credentials will be managed using Vault.

## Instructions
**You must use GCP for Homework 6 and Homework 7 due to AWS Educate limitations.  You will NOT be able to use AWS for this assignment.**

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
8. Commit the empty main.tf file to GitHub.  Enter a comment when prompted using your text editor.
```
git commit -a
```
9. Push your changes to GitHub.
```
git push
```
10. Verify that your changes pushed to GitHub by visiting your repository in your web browser.  i.e. https://github.com/yourgithubname
11. Copy/Paste the following text into your main.tf file.  This will set up your Terraform to use the Google Provider, provision a VPC network for Homework 7 and build multiple VMs.

```
terraform {
  required_providers {
    google = {
      source = "hashicorp/google"
    }
  }
}

provider "google" {
  version = "3.5.0"
  credentials = file(var.credentials_file)
  project = var.project
  region = var.region
  zone = var.zone

}

resource "google_compute_network" "vpc_network" {
  name = "homework7-network"
}

resource "google_compute_address" "vm_static_ip" {
  name = "homework7-static-ip"
}


resource "google_compute_instance" "vm_instance" {
  name         = "homework7-instance1"
  machine_type = var.machine_types[var.environment]
  tags         = ["web", "dev"]

  provisioner "local-exec" {
     command = "echo ${google_compute_instance.vm_instance.name}:  ${google_compute_instance.vm_instance.network_interface[0].access_config[0].nat_ip} >> ip_address.txt"
  }

  boot_disk {
    initialize_params {
      image = "cos-cloud/cos-stable"
    }
  }

  network_interface {
    network = google_compute_network.vpc_network.self_link
    access_config {
      nat_ip = google_compute_address.vm_static_ip.address
    }
  }
}
"google_compute_instance" "vm_instance" {
  name         = "homework7-instance2"
  machine_type = var.machine_types[var.environment]
  tags         = ["web", "dev"]

  provisioner "local-exec" {
     command = "echo ${google_compute_instance.vm_instance.name}:  ${google_compute_instance.vm_instance.network_interface[0].access_config[0].nat_ip} >> ip_address.txt"
  }

  boot_disk {
    initialize_params {
      image = "cos-cloud/cos-stable"
    }
  }

  network_interface {
    network = google_compute_network.vpc_network.self_link
    access_config {
      nat_ip = google_compute_address.vm_static_ip.address
    }
  }
}
"google_compute_instance" "vm_instance" {
  name         = "homework7-instance3"
  machine_type = var.machine_types[var.environment]
  tags         = ["db", "dev"]

  provisioner "local-exec" {
     command = "echo ${google_compute_instance.vm_instance.name}:  ${google_compute_instance.vm_instance.network_interface[0].access_config[0].nat_ip} >> ip_address.txt"
  }

  boot_disk {
    initialize_params {
      image = "cos-cloud/cos-stable"
    }
  }

  network_interface {
    network = google_compute_network.vpc_network.self_link
    access_config {
      nat_ip = google_compute_address.vm_static_ip.address
    }
  }
}
"google_compute_instance" "vm_instance" {
  name         = "homework7-instance4"
  machine_type = var.machine_types[var.environment]
  tags         = ["db", "dev"]

  provisioner "local-exec" {
     command = "echo ${google_compute_instance.vm_instance.name}:  ${google_compute_instance.vm_instance.network_interface[0].access_config[0].nat_ip} >> ip_address.txt"
  }

  boot_disk {
    initialize_params {
      image = "cos-cloud/cos-stable"
    }
  }

  network_interface {
    network = google_compute_network.vpc_network.self_link
    access_config {
      nat_ip = google_compute_address.vm_static_ip.address
    }
  }
}
```
2.



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
