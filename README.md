# nginx-webserver-deployment
Nginx Webserver deployment in AWS

Step 1: Launch an EC2 Instance

- Navigate to the EC2 Dashboard in the AWS Console.

- Click on Launch Instance and configure the same.

Name: Enter a name for your instance.
AMI: Select an Amazon Machine Image (e.g., Amazon Linux 2 or Ubuntu).
Instance Type: Choose a type like t2.micro (free-tier eligible).
Key Pair: Create or select a key pair for SSH access.
Network Settings: Allow HTTP (port 80) and SSH (port 22) traffic.
Click Launch Instance.

Step 2: Connect to Your EC2 Instance

- Open your terminal or SSH client and connect to your instance using:

ssh -i your-key.pem ec2-user@your-instance-public-ip

- Replace your-key.pem with your key pair file and your-instance-public-ip with the public IP address of your instance.

Step 3: Install Nginx on the Instance

- Update the package list and install nginx

sudo apt update -y   # For Ubuntu
sudo apt install nginx -y   # For Ubuntu

- Start the Nginx service:

sudo systemctl start nginx

Step 4: Configure Security Group for HTTP Traffic

- Select your instance on EC2 dashboard and click on the Security Group linked to it.

- Edit inbound rules to ensure port 80 (HTTP) is open:

Type: HTTP
Protocol: TCP
Port Range: 80
Source: Anywhere (0.0.0.0/0)

Step 5: Test Your Deployment

- Open a browser and enter the public IP address of your EC2 instance.

You should see the default Nginx welcome page. Now replace it with the new web page you want to deploy.
