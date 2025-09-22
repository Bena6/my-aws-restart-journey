### EC2 Web Server with Load Balancer
In this project I launch an EC2 instance, deploy a small web app, configure security groups, connect via SSH key pairs, and add a load balancer.

### Step 1: Launch an EC2 Instance

Go to AWS Console → EC2 → Instances → Launch Instance.

Name: my-webserver.

Choose Amazon Linux 2 AMI (Free tier eligible).

Instance type: t2.micro (Free tier).

#### Key pair:

Create a new key pair my-keypair.

Download .pem file (keep it safe — we’ll need it for SSH).

#### Security group:

Allow SSH (22) from your IP.

Allow HTTP (80) from anywhere (0.0.0.0/0).

Click launch instance.

### Step 2: Connect to Instance

In the EC2 console, select instance → Connect.

Copy the Public IPv4 address.

In the terminal, run: chmod 400 my-keypair.pem

ssh -i my-keypair.pem ec2-user@<PUBLIC_IP>

We are now inside the EC2 instance.

### Install and Run a Web Server

Simple static site with Apache:

sudo yum update -y

sudo yum install -y httpd

sudo systemctl start httpd

sudo systemctl enable httpd

echo "Hello from EC2 Web Server" | sudo tee /var/www/html/index.html

Now let's open http://<PUBLIC_IP> in the browser — should see the message created.

### Step 4: Explore Security Groups

Go to EC2 → Security Groups.

Modify rules:

Try removing HTTP (80) and see your app stop being accessible.

Add it back to restore access.

This shows how security groups act like a firewall.

### Step 5: Add a Load Balancer (Bonus)

In EC2 → Load Balancers → Create Load Balancer.

Choose Application Load Balancer.

Name: my-alb.

Scheme: Internet-facing.

Listeners: HTTP (80).

Security group: allow HTTP (80).

Create a Target Group → Register the EC2 instance.

Complete setup.

Now instead of hitting the instance’s public IP, we'll use the Load Balancer DNS name (shown in the console).

### Step 6: Clean up

Terminate EC2 instance.

Delete load balancer & target group.

Remove unused key pairs.

### What I've learnt

Launching and connecting to EC2 instances.

Using SSH keys to securely access servers.

Configuring security groups for inbound rules.

Deploying a basic web server (Apache)

Using an Application Load Balancer to route traffic.
