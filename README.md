📌 Lab 5 – EC2 Application Connected to RDS PostgreSQL
📖 Overview

This project demonstrates deployment of an EC2-hosted Orchard Core application connected to Amazon RDS PostgreSQL. The application performs full CRUD operations.

🏗 Architecture

User → Internet → EC2 (Public Subnet)
EC2 → RDS PostgreSQL (Private Subnet)

Security:

EC2 allows HTTP (80)

RDS allows PostgreSQL (5432) from EC2 Security Group only

⚙ Deployment Steps

Launch EC2 instance (Ubuntu 24.04)

Install .NET and deploy Orchard Core

Create RDS PostgreSQL instance

Configure RDS Security Group:

Type: PostgreSQL

Port: 5432

Source: EC2 Security Group

Connect Orchard to RDS using:

Host: orchard-db.xxxxx.ap-south-1.rds.amazonaws.com

Port: 5432

SSL Mode: Require

Complete setup

🗄 Database Configuration

Engine: PostgreSQL

Port: 5432

Hosted on Amazon RDS

SSL Enabled

🔁 CRUD Operations Demonstrated

✔ Create – Blog post added
✔ Read – Blog displayed on homepage
✔ Update – Blog title edited
✔ Delete – Blog removed

Screenshots available in /screenshots folder.

🔐 Security Configuration

RDS Inbound Rule:
PostgreSQL | 5432 | Source: launch-wizard-3 (EC2 Security Group)

No public database access allowed.

🌐 Access

Application hosted on EC2 Public IP: http://<your-ec2-public-ip>
