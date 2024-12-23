# altschool-second-semester-project
I provisioned a server and set up a simple landing page to demonstrate my team’s capabilities to potential investors.

Public IP Address: 3.84.250.118
Public Domain Name: rawlingsaltschool.mooo.com

#How to Host an HTML Webpage On an AWS EC2 Server

Step 1: Setup EC2 Instance on AWS and Launch it
Amazon Web Services (AWS) Elastic Compute Cloud (EC2) allows users to create virtual servers, called instances, to run applications on the cloud. Setting up an EC2 instance might seem daunting initially, but this guide will walk you through the process step-by-step. To set up an EC2 instanc. Set-up an EC2 instance with the following steps.
1. Go to the AWS Management Console.
2. Sign in with your AWS credentials. If you don’t have an account, create one by clicking Create a Free Account.
3. Once logged in, search for EC2 in the search bar at the top of the AWS Management Console.
4. Click EC2 to open the EC2 Dashboard.
5. On the EC2 Dashboard, click Launch Instance.
6. Provide a name for your instance
7. Select an AMI that determines the operating system and software configuration of your instance. Common choices include:
8. Amazon Linux 2 (default for many cases).
   Ubuntu Server.
   Microsoft Windows Server.
9. Click Select next to your preferred AMI.
10. Select the instance type based on your application’s requirements. The most common types are:
    t2.micro: Free-tier eligible and suitable for lightweight applications.
    t3.medium or higher: For more demanding workloads.
11. Click Next: Configure Instance Details.
12. Define firewall rules to allow or restrict access to your instance:
    Type: Select protocols like SSH (22), HTTP (80), or HTTPS (443).
    Source: Specify IP ranges (e.g., 0.0.0.0/0 for global access or your IP for restricted access).
13. Create a new key pair or use an existing one:
    Key Pair Name: Enter a name for your key pair.
    Download Key Pair: Save the .pem file securely; you’ll need it to connect to your instance.
14. Click Launch Instances.

Step 2: Connect to the Instance
You can connect to the instance using the AWS CLI or using SSH. SSH into the EC2 instance using your key pair:
ssh -i your-key.pem ec2-user@your-ec2-public-ip

Step 3: Install a Web Server
Install Apache or Nginx:
   For Apache:
      sudo yum install httpd -y   # For Amazon Linux
      sudo service httpd start
   For Nginx:
      sudo apt update
      sudo apt install nginx -y
      sudo service nginx start

Step 4: Place your HTML files in the server's document root:
For Apache:
   sudo mv your-file.html /var/www/html/index.html
For Nginx:
   sudo mv your-file.html /usr/share/nginx/html/index.html

Step 5: Access your website
Copy the public IP address of your Instance, pase it on your browser and access your webpage.
