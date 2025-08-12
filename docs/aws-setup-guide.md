# 🚀 AWS Setup Guide

This guide walks you through setting up the **Cloud Monitoring Dashboard**.

---

# Section 1: Prerequisites 📝

**What you need:**

- AWS account (free tier is fine)
- Email address for receiving alerts
- 30-60 minutes of time
- Basic AWS console knowledge (can navigate and click buttons)
- AWS Pricing Calculator (webaccess for cost estimates)

**Permissions needed:**

- Access to CloudWatch, SES, SNS services
- If you're not the account owner, ask for these permissions

**Cost warning:** This setup uses mostly free services, but check your billing dashboard after setup.

---

# Section 2: Step-by-Step Guide 📖

## 1️⃣ Launch an EC2 Instance

**Time needed: 10 minutes**

### 💡 What You’re Doing

Creating a small server that we'll monitor with our dashboard.

### 🛠️ Steps

1. Go to AWS Console → Search "EC2" → Click EC2
2. Click "Launch instance" and provide a name for your server
3. Choose "Amazon Linux 2 AMI" (free tier eligible)
4. Choose "t2.micro" or "t3.micro" instance type which are free-tier eligible
5. Keep default settings → Click "Launch instance"
6. Wait 2-3 minutes for instance to start running

### ✅ How You Know It Worked

- Instance appears as **running** in EC2 console

![EC2 instance successfully running in the AWS Management Console.](/screenshots/01_ec2_running.png)  
_EC2 instance successfully running in the AWS Management Console._

---

## 2️⃣ Check EC2 Metrics in CloudWatch (No setup needed)

**Time needed: 5 minutes**

### 💡 What You’re Doing

Verifying your EC2 instance’s default performance metrics (CPU, network, disk) are visible in CloudWatch.

### 🛠️ Steps

1. Navigate to CloudWatch → Metrics
2. Go to EC2 → Per-Instance Metrics
3. Find your EC2 instance ID and confirm metrics like:
   `CPUUtilization`
   `NetworkIn` / `NetworkOut`
   `DiskReadBytes` / `DiskWriteBytes`

### ✅ How You Know It Worked

- Metrics graphs show data points after a few minutes
- No extra setup is required to collect these basic metrics

![Viewing basic EC2 performance metrics in CloudWatch.](/screenshots/02_cloudwatch_ec2_metrics.png)  
_Viewing basic EC2 performance metrics in CloudWatch._

---

## 3️⃣ Create CloudWatch Alarms

**Time needed: 10 minutes each alarm**

### 💡 What You’re Doing

Setting up automatic alerts when certain metrics exceed safe thresholds.

### 🛠️ Steps

1. Go to **CloudWatch → Alarms → Create alarm**
2. Choose a metric (e.g., `CPUUtilization`)
3. Set a threshold (e.g., CPU > 80% for 5 minutes)
4. Choose notification via **SNS topic**
5. Name and create the alarm

### ✅ How You Know It Worked

- Alarm status shows as **OK**
- You receive a notification when you intentionally stress the server

![Creating a CPU utilization alarm in CloudWatch to trigger notifications.](/screenshots/03_cloudwatch_alarm.png)  
_Creating a CPU utilization alarm in CloudWatch to trigger notifications._

---

## 4️⃣ Set Up SNS Notifications

**Time needed: 5 minutes**

### 💡 What You’re Doing

Creating a channel for CloudWatch to send alerts.

### 🛠️ Steps

1. Go to **SNS → Topics → Create topic**
2. Type: **Standard**
3. Name: `monitoring-alerts`
4. Create the topic
5. Add a subscription:
   - Protocol: **Email**
   - Endpoint: Your email address
6. Confirm the subscription via the email AWS sends you

### ✅ How You Know It Worked

- Subscription shows as **Confirmed** in SNS console
- You receive an email when an alarm triggers

![Setting up an SNS topic for CloudWatch alarms to send alerts via email.](/screenshots/04_sns_topic.png)  
_Setting up an SNS topic for CloudWatch alarms to send alerts via email._

---

## 5️⃣ Configure SES for Email Alerts

**Time needed: 5 minutes**

### 💡 What you're doing

Setting up AWS to send you alert emails.

### 🛠️ Steps

1. Go to AWS Console → Search "SES" → Click Simple Email Service
2. Click the left side hamburger menu. Then under configuration banner, select "identities"
3. Click "Create identity"
4. Choose "Email address"
5. Enter your email address → Click "Create identity"
6. **Go check your email** → Click the verification link
7. Come back to AWS → Your email should show "Verified"

### ✅ How to know it worked

Your email shows green checkmark and says "Verified"

![Verifying your email address in AWS SES for sending alerts.](/screenshots/05_ses_email_verified.png)  
_Verifying your email address in AWS SES for sending alerts._

---

## 6️⃣ Create a CloudWatch Dashboard

**Time needed: 15 minutes**

### 💡 What you're doing

Creating a page where you can see all your server metrics.

### 🛠️ Steps

1. Go to **CloudWatch → Dashboards → Create dashboard**
2. Name: `business-ops-dashboard`
3. Add widgets/line charts for:
   - CPU utilization
   - Network traffic
   - Disk activity
4. Save dashboard

### ✅ How You Know It Worked

- Dashboard shows live graphs for all selected metrics. If charts are empty, wait 5-10 minutes for data to populate.

![Starting a new CloudWatch dashboard to display monitoring widgets.](/screenshots/06_cloudwatch_dashboard_create.png)  
_Starting a new CloudWatch dashboard to display monitoring widgets._

![Final monitoring dashboard showing CPU, network, and disk activity graphs.](/screenshots/07_dashboard_widgets.png)  
_Final monitoring dashboard showing CPU, network, and disk activity graphs._

---

# Section 3: Troubleshooting ⚙️

- **No metrics?** Check EC2 IAM role permissions for CloudWatch
- **No alerts?** Verify SNS subscription and SES email settings
- **Slow data updates?** CloudWatch metrics may take 5 minutes to refresh

---
