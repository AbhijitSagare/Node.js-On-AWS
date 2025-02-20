# Deploy simple node application on aws ec2 instance

This guide provides step-by-step instructions to **install Node.js, clone a GitHub repository, and deploy a Node.js application** on an AWS EC2 instance.  

---

## 📌 Prerequisites

Before you begin, ensure you have:
- An **AWS EC2 instance** (Ubuntu 22.04 preferred)
- SSH access to the EC2 instance
- A **GitHub repository** with your Node.js project.

## 1️⃣ **Connect to EC2 and Gain Superuser Access**

First, connect to your **EC2 instance** using SSH:

```bash
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```
Once connected, run the following command to gain superuser (root) access:

```bash
sudo su
```

2️⃣ Install Node.js and npm
Update the package manager and install Node.js and npm:

```bash
sudo apt update
sudo apt install nodejs
sudo apt install npm
```
This installs the latest stable version of Node.js.

Now verify the installation:


```bash
node -v   # Check Node.js version
npm -v    # Check npm version

```

4️⃣ Clone the Node.js Project from GitHub
Run the following command to clone the repository:

```bash
https://github.com/AbhijitSagare/Node.js-On-AWS.git
```
Navigate into the project directory

```bash
cd Node.js-On-AWS
``` 

5️⃣ Install Dependencies and Start the Application
Run the following commands:

```bash
npm install
node server.js
```

# Your application is now running on port 4000. 🎉

6️⃣ Allow Public Access to Port 4000

By default, AWS blocks external access to ports. Follow these steps to allow public access to port 4000:

Open AWS Management Console

Go to EC2 Dashboard → Click on your Instance

Click on the Security Group associated with the instance
Click Edit Inbound Rules
Add a new rule:
Type: Custom TCP
Port: 4000
Source: 0.0.0.0/0 (to allow all)
Click Save Rules

7️⃣ Access Your Application in a Browser
Find your EC2 Public IP Address from the AWS console.

Open the browser and enter:

```bash
http://your-ec2-public-ip:4000/
```


# Your Node.js application is now live on AWS! 🚀








