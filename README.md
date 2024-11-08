# Three-Tier Architecture Web Application

This repository contains the setup and configuration of a **Three-Tier Architecture** web application deployed on AWS, using EC2 for the presentation layer, Lambda functions for the application layer, and DynamoDB or RDS for the data layer. The project aims to showcase the implementation of a secure and scalable web application infrastructure using AWS services.

![Screenshot 2024-11-09 002623](https://github.com/user-attachments/assets/8def5c93-48a1-4d01-ae8e-11ca3d90e8ea)

## Architecture Overview

The application is based on a **Three-Tier Architecture** with the following layers:

1. **Presentation Layer**: 
   - **Amazon EC2** instance hosting a web application (e.g., static HTML page or dynamic web app).
   - **Web Server** (Apache or Nginx) serves the frontend.

2. **Application Layer**:
   - **AWS Lambda Functions** that handle business logic, triggered via **API Gateway**.
   - These functions interact with the database layer for data operations (CRUD).

3. **Data Layer**:
   - **Amazon RDS** (MySQL/PostgreSQL) or **Amazon DynamoDB** is used to store and retrieve data.

4. **Network Layer**:
   - A **VPC** (Virtual Private Cloud) isolates and secures resources with public and private subnets.

---

## Prerequisites

Before setting up the project, make sure you have the following:

- An **AWS account**.
- AWS CLI installed and configured.
- Basic knowledge of AWS services like EC2, Lambda, API Gateway, VPC, and DynamoDB/RDS.
- **Postman** (for API testing).
- **SSH access** to EC2 instance.
- **Knowledge of HTML, JavaScript, and Node.js** (for API and frontend development).

---

## Setup Instructions

### 1. **Launch EC2 Instance (Presentation Layer)**

- Go to the **AWS Management Console** > **EC2** and launch a new instance in your **Public Subnet**.
- **Install a Web Server**:
  - SSH into the EC2 instance.
  - Run the following commands to install **Apache** (or Nginx):

    **For Apache**:
    ```bash
    sudo apt update
    sudo apt install apache2 -y
    sudo systemctl start apache2
    sudo systemctl enable apache2
    ```

    **For Nginx**:
    ```bash
    sudo apt update
    sudo apt install nginx -y
    sudo systemctl start nginx
    sudo systemctl enable nginx
    ```

- Upload your **HTML** web application to the EC2 instance:
  ```bash
  scp -i "path-to-your-key.pem" index.html ubuntu@<EC2-public-IP>:/var/www/html/

# aws stage URL- https://ehqrl4j558.execute-api.ap-southeast-2.amazonaws.com/dev


