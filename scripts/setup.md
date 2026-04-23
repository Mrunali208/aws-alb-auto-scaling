#  Setup Guide – ALB + Auto Scaling Project

## 1. Launch EC2 Instance

* Go to AWS Console → EC2 → Launch Instance
* Choose Ubuntu AMI
* Instance type: t3.micro
* Configure Security Group:

  * Allow HTTP (80)
  * Allow SSH (22)

---

## 2. Create Launch Template

* Go to EC2 → Launch Templates → Create
* Add User Data:

```
#!/bin/bash
apt update -y
apt install -y apache2
systemctl start apache2
systemctl enable apache2
echo "<h1>Auto Scaled Server - $(hostname)</h1>" > /var/www/html/index.html
```

---

## 3. Create Target Group

* EC2 → Target Groups → Create
* Type: Instances
* Protocol: HTTP (Port 80)
* Register EC2 instance

---

## 4. Create Application Load Balancer

* EC2 → Load Balancers → Create
* Type: Application Load Balancer
* Scheme: Internet-facing
* Select 2 Availability Zones
* Attach Target Group

---

## 5. Create Auto Scaling Group

* EC2 → Auto Scaling Groups → Create
* Select Launch Template
* Attach to Target Group
* Set capacity:

  * Desired: 2
  * Min: 1
  * Max: 3

---

## 6. Configure Scaling Policy

* Target tracking
* Metric: CPU Utilization
* Target: 50%

---

## 7. Testing

* Open Load Balancer DNS
* Refresh multiple times
* Observe different instance responses

---

##  Result

* Traffic distributed across instances
* Auto Scaling adds/removes instances automatically
* High availability achieved
