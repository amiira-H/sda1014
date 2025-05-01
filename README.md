# 🚀 Clarusway IE Bootcamp-assignment9 
## 👩‍💻 Student: Amira Hamoud

1. Created S3 Bucket: `amira1014-clarusway-assets` in `eu-north-1`
2. Uploaded:
   - `index.html`
   - `logo.png`
   - `sda.png`
3. Enabled **Static Website Hosting**
4. Added **Bucket Policy** for public access
### 🔗 S3 Website URL
http://amira1014-clarusway-assets.s3-website.eu-north-1.amazonaws.com

 
Part 2: Auto Scaling Group (ASG)
✅ Tasks Performed:
Launch Template Created

User Data Script:
#!/bin/bash
yum update -y
yum install nginx -y
systemctl start nginx
systemctl enable nginx
aws s3 cp s3://amira1014-clarusway-assets/index.html /usr/share/nginx/html/
ASG Configuration

Min: 1

Desired: 2

Max: 3

Health checks: EC2 + ELB

Part 3: Application Load Balancer (ALB)
Created Internet-facing ALB
Listener: HTTP (Port 80)
Target Group: TargetGroup
Health Check Path: /

Verified Load Balancing
Used curl multiple times to confirm round-robin instance switching
(curl ALB-as-2104248431.eu-north-1.elb.amazonaws.com)
