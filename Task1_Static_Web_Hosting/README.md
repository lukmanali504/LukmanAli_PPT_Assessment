## Objective
Deploy a basic static website on an Ubuntu EC2 instance using Nginx web server.

## Steps

1. Launch an EC2 instance
   - AMI: Ubuntu Server 22.04
   - Instance type: t2.micro
   - Allow ports: 22 (SSH), 80 (HTTP)

2. Connect to instance using SSH
   ssh -i keypair.pem ubuntu@<Public-IP>

3. Update packages
   sudo apt update -y

4. Install Nginx
   sudo apt install nginx -y

5. Start and enable Nginx
   sudo systemctl start nginx
   sudo systemctl enable nginx

6. Create website file
   sudo nano /var/www/html/index.html

7. Add HTML content
   <html>
   <head><title>My Website</title></head>
   <body>
   <h1>Website Hosted on EC2</h1>
   <p>Nginx server is working.</p>
   </body>
   </html>

8. Restart Nginx
   sudo systemctl restart nginx

9. Open browser and access
   http://<Public-IP>

## Result
The website is successfully accessible through the EC2 public IP address in the browser.