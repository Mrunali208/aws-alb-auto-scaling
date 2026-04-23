#  Scalable Web Application using ALB & Auto Scaling (AWS)

##  Project Overview

This project demonstrates how to build a **highly scalable and fault-tolerant web application** on AWS using Application Load Balancer and Auto Scaling Group.

The system automatically distributes traffic and dynamically adjusts the number of servers based on demand.

---

##  Objective

- Handle high traffic without downtime
- Automatically scale infrastructure
- Implement real-world cloud architecture

---

##  Tech Stack

- AWS EC2
- Application Load Balancer (ALB)
- Auto Scaling Group (ASG)
- Target Groups
- Ubuntu + Apache

---

##  Architecture

User → Load Balancer → Target Group → Auto Scaling → EC2 Instances

---

##  Features

- Load balancing across multiple instances
- Automatic scaling based on CPU usage
- Health checks and self-healing system
- High availability across multiple zones

---

##  How It Works

1. User sends request
2. Load Balancer distributes traffic
3. Auto Scaling launches instances based on demand
4. Unhealthy instances are replaced automatically

---

##  Screenshots

### EC2 Instances
![EC2](screenshots/ec2.png)

### Load Balancer
![ALB](screenshots/alb.png)

### Target Group Health
![Target](screenshots/target.png)

### Auto Scaling Group
![ASG](screenshots/asg.png)

---

##  Learning Outcomes

- Deep understanding of AWS scalability
- Load balancing concepts
- Auto Scaling strategies
- Real-world cloud architecture design

---

##  Future Improvements

- Add CI/CD pipeline
- Use Docker + ECS
- Add CloudFront CDN
- Attach custom domain

---

##  Author
Mrunali Patil  
