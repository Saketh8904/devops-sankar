# devops-sankar
# AWS DevOps Engineer Intern Assignment

![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04-E95420)
![Nginx](https://img.shields.io/badge/Nginx-Web_Server-009639)
![Docker](https://img.shields.io/badge/Docker-Installed-2496ED)
![GitHub](https://img.shields.io/badge/GitHub-Repository-black)

## Project Overview

This repository contains my submission for the **AWS DevOps Engineer
Intern Assignment**. The objective was to deploy a static website on an
Ubuntu EC2 instance using Nginx, perform basic Linux administration,
document the deployment, and complete all available bonus tasks.

**Author:** Saketh Alevooraya K\
**College:** Sir M. Visvesvaraya Institute of Technology\
**Branch:** Computer Science & Engineering

------------------------------------------------------------------------

## Repository Structure

``` text
.
├── index.html
├── README.md
└── screenshots
    ├── instance-dashboard.png
    ├── ec2-ipdetails.png
    ├── ssh-login.png
    ├── nginx-running.png
    ├── nginx-run-on-web.png
    ├── html-code.png
    ├── html-on-web.png
    ├── elasticip-alloc.png
    ├── elastic-ip-webimg.png
    ├── add-secgroup.png
    ├── docker-helloworld.png
    └── shell-script-restart-nginx.png
```

------------------------------------------------------------------------

## AWS Services Used

-   Amazon EC2
-   Security Groups
-   Elastic IP
-   VPC (Default)
-   Internet Gateway

------------------------------------------------------------------------

## Task 1 -- EC2 Setup

-   Launched an Ubuntu EC2 instance.
-   Configured a Security Group allowing:
    -   SSH (22)
    -   HTTP (80)
-   Connected to the instance using SSH.

``` bash
ssh -i "devops-sankar-kp.pem" ubuntu@<EC2-PUBLIC-IP>
```

------------------------------------------------------------------------

## Task 2 -- Linux Basics

Updated packages:

``` bash
sudo apt update
sudo apt upgrade -y
```

Installed Nginx:

``` bash
sudo apt install nginx -y
```

Managed the service:

``` bash
sudo systemctl start nginx
sudo systemctl enable nginx
sudo systemctl status nginx
sudo systemctl restart nginx
```

System monitoring:

``` bash
df -h
free -h
ps aux
top
```

Verified the default Nginx page using the EC2 public IP.

------------------------------------------------------------------------

## Task 3 -- Website Deployment

Copied the custom HTML page to the Nginx web root.

``` bash
sudo cp index.html /var/www/html/index.html
sudo systemctl restart nginx
```

The page displays:

-   Name
-   College
-   Branch
-   Email
-   Current Date

------------------------------------------------------------------------

## Task 4 -- Git & GitHub

``` bash
git init
git add .
git commit -m "Initial Commit"
git branch -M main
git remote add origin https://github.com/Saketh8904/devops-sankar.git
git push -u origin main
```

------------------------------------------------------------------------

## Bonus Tasks

### Elastic IP

Allocated and associated an Elastic IP with the EC2 instance to provide
a static public IP.

### Additional Security Group

Created another Security Group and attached it to the EC2 instance.

### Docker

Installed Docker and verified the installation.

``` bash
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
sudo docker run hello-world
```

### Shell Script

Created `restart-nginx.sh`

``` bash
#!/bin/bash
echo "Restarting Nginx..."
sudo systemctl restart nginx
sudo systemctl status nginx --no-pager
echo "Restart Completed Successfully"
```

Run using:

``` bash
chmod +x restart-nginx.sh
./restart-nginx.sh
```

------------------------------------------------------------------------

## Screenshots

The `screenshots/` directory contains:

-   EC2 Dashboard
-   EC2 IP Details
-   SSH Login
-   Nginx Running
-   Default Nginx Page
-   HTML Source
-   Hosted Website
-   Elastic IP Allocation
-   Website via Elastic IP
-   Additional Security Group
-   Docker Hello World
-   Shell Script Execution

------------------------------------------------------------------------

## Learning Outcomes

-   AWS EC2 provisioning
-   Linux administration
-   Nginx configuration
-   Static website hosting
-   SSH connectivity
-   Git & GitHub workflow
-   Docker basics
-   Elastic IP management
-   Security Group configuration
-   Shell scripting

------------------------------------------------------------------------

## Cleanup

After completing the assignment:

-   Released the Elastic IP.
-   Terminated the EC2 instance.
-   Removed unused AWS resources to avoid charges.

------------------------------------------------------------------------

## Author

**Saketh Alevooraya K**

GitHub: https://github.com/Saketh8904
