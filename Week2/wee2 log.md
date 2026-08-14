# Week 2 — EC2 + Linux + Networking + Nginx Cheat Sheet


# ☁️ 1. EC2 — Virtual Server

EC2 = Elastic Compute Cloud

AWS gives you a virtual Linux server.
AWS
 │
 └── EC2
      │
      └── Ubuntu Linux
           │
           └── Nginx

You can connect to it using SSH and manage it like a normal Linux computer.


# 💿 2. AMI — Operating System Template

AMI = Amazon Machine Image

It's the template used to create your EC2.

Ubuntu AMI
    ↓
Create EC2
    ↓
Ubuntu Linux Server

Think: AMI = starting template for your server.


# 🌐 3. VPC + Subnet

[VPC]

VPC = Virtual Private Cloud

Your virtual network inside AWS.

[Subnet]

A smaller network inside the VPC.

AWS
 │
 └── VPC
      │
      ├── Public Subnet
      │      │
      │      └── EC2
      │
      └── Private Subnet

Think:

VPC = big network

Subnet = smaller section of that network


# 🔥 4. Security Group

A Security Group = virtual firewall for EC2.

Example:
Inbound Rules

SSH    TCP  22    Your IP
HTTP   TCP  80    Anywhere

Port 22 → SSH
Your PC
   │
   │ SSH :22
   ↓
 EC2

 Port 80 → Website
 Browser
   │
   │ HTTP :80
   ↓
 EC2
   ↓
Nginx


# 🔑 5. SSH

SSH = Secure Shell

Used to remotely connect to your Linux server.

# ---------------- ssh -i "D:\Vihara DevOps\.ssh\cloudops-inventory-key.pem" ubuntu@YOUR_PUBLIC_IP 

ssh       → connect remotely
-i        → use private key
.pem      → your private SSH key
ubuntu    → Linux username
PUBLIC_IP → EC2's internet address


# 🔐 6. .pem Key

Your .pem is your private SSH key.

AWS Key Pair
     │
     ├── Public key → EC2
     │
     └── Private key → Your computer

⚠️ Never upload .pem to GitHub.

You can keep multiple keys:

.ssh/
├── project1-key.pem
├── project2-key.pem
└── test-server-key.pem


# 🌍 7. Nginx

Nginx = Web Server

It receives browser requests and sends your website files.

Browser
   │
   │ HTTP
   ↓
EC2
   │
   ↓
Nginx
   │
   ↓
index.html

# codes to install

sudo apt update
sudo apt install nginx -y

# check

sudo systemctl status nginx


# Copy your HTML to EC2

From your local VS Code terminal, not from inside SSH, run:

# ------------------- scp -i "C:\Users\YOUR_NAME\.ssh\cloudops-inventory-key.pem" website/index.html ubuntu@YOUR_PUBLIC_IP:/tmp/index.html

This means:

Copy my local website/index.html to the EC2 server.

# SSH into EC2 again

ssh -i "C:\Users\YOUR_NAME\.ssh\cloudops-inventory-key.pem" ubuntu@YOUR_PUBLIC_IP

Then:

ls -l /tmp/index.html

You should see your file.

# Put it where Nginx serves websites

Run:

sudo cp /tmp/index.html /var/www/html/index.html

Then:

sudo systemctl reload nginx

Now open:

http://YOUR_PUBLIC_IP

You should see your Inventory System page.

🎉 That's your first project deployment.




# ⚙️ 8. Nginx Service Commands

[Start]

sudo systemctl start nginx

[Stop]

sudo systemctl stop nginx

[Restart]

sudo systemctl restart nginx

[Reload] configuration

sudo systemctl reload nginx


# 📄 9. Nginx Website Files

Ubuntu's typical Nginx web directory:

/var/www/html/

[Check:]

ls -la /var/www/html/

Main webpage:

/var/www/html/index.html



# 📊 11. Nginx Logs

Access log

sudo tail -20 /var/log/nginx/access.log

[Shows:]

Who accessed my website and what happened?

[Live:]

sudo tail -f /var/log/nginx/access.log

[Stop:]

Ctrl + C

Error log

sudo tail -20 /var/log/nginx/error.log

Shows:

What errors did Nginx encounter?


# 🔍 12. Troubleshooting Commands

Nginx status

sudo systemctl status nginx

Service history/logs

sudo journalctl -u nginx

Recent logs:

sudo journalctl -u nginx --since "30 minutes ago"

Is port 80 listening?

sudo ss -tulpn | grep :80

Test Nginx locally

curl http://localhost

If this returns your HTML:

EC2 → Nginx → HTML ✅
