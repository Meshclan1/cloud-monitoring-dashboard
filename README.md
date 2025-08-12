# 📝 Cloud Monitoring Dashboard

**A simple AWS monitoring solution for small businesses using CloudWatch and email alerts.**

## 🎯 Business Problem

```
Small businesses using AWS often don't know when their servers have problems until customers complain. They also get surprised by unexpected AWS bills at the end of the month. This can cost them customers and money.
```

## 💡 Solution Overview

I am building a monitoring dashboard using AWS CloudWatch that:

- Shows server performance in real-time
- Sends email alerts when something goes wrong
- Tracks AWS spending to prevent bill surprises

Perfect for small businesses with 1-5 servers who want basic monitoring without expensive tools.

## ✨ Key Features

- **Server Monitoring** - Track CPU, memory, and disk usage
- **Email Alerts** - Get notified when servers have problems
- **Cost Tracking** - Monitor AWS spending with budget alerts
- **Simple Dashboard** - Easy-to-read charts and graphs
- **Mobile Friendly** - Check status from your phone

## 🛠️ Tech Stack

- **Amazon CloudWatch** - For collecting metrics and creating dashboards
- **Amazon SES** - For sending email alerts (cheap and reliable)
- **Amazon SNS** - For routing notifications
- **AWS IAM** - For security permissions

**Why these services?** They work well together and most are included in AWS free tier.

## 🏗️ Architecture

**How it works:**

1. CloudWatch collects data from your servers
2. When something goes wrong, it triggers an alarm
3. The alarm sends a message through SNS
4. You get an email alert via SES
5. You can view everything on the CloudWatch dashboard

Full technical details:

## 🏃 Quick Start

**What you need:**

- AWS account
- Email address for alerts

**Setup steps:**

1. Verify your email in AWS SES
2. Create CloudWatch dashboard
3. Set up alarms and notifications
4. Test that alerts work

**Time needed:** About 30 minutes

📋 **Detailed instructions:**

## 📸 Screenshots

## 📊 Results

**Before this project:**

- No idea when servers had problems
- Found out about issues from customers
- Surprised by AWS bills

**After this project:**

- Get email alerts within 2 minutes of problems
- Can see server status anytime on dashboard
- Get warnings before AWS bill gets too high
- Prevented 2 potential outages in first month of testing

## 🔧 Challenges Overcome

## 🎓 Lessons Learned

**AWS Skills I Developed:**

- Setting up CloudWatch dashboards and alarms
- Configuring SES for email delivery
- Basic IAM permissions for security
- Understanding AWS free tier limits
- Documenting cloud project from start to beginning via Github

**Cost Management Lessons:**

- Always check if your free tier has expired before starting
- Use AWS Pricing Calculator to estimate costs by region
- Different AWS regions have different pricing (learned London can be more expensive)
- Set up billing alerts BEFORE you start building, not after

**General Lessons:**

- Start simple and add features gradually
- Taking screenshots at verification points (moments that prove each step worked correctly!)
- Test everything before marking it as completed
- Documentation is important!
- Regional selection affects both cost and latency
- Cost monitoring should be built in from day one

## 🚀 Future Improvements

**What I'd do differently next time:**

- Check free tier status and regional pricing before any AWS work
- Set up cost alerts on day one
- Add more types of alerts (disk space, network issues)
- Create better-looking dashboards connected to a python module or using javascript libraries
- Set up automatic responses to common problems
- Learn Infrastructure as Code for quicker deployments(CloudFormation)
- Create a cloud template for chosen IDE (VSCode). (Helps make building projects from scratch much quicker!)
- In README.md section, number each section for easier reference

**Would be cool to add:**

- Notifications via different portals - ie if using teams, one gets a notification
- Automatic server restart for some problems to reduce manual involvement
- Integration with important business metrics (sales, orders)

**Learning goals:**

- Get better at designing and implementing Infrastructure as Code
- Learn more about AWS security
- Understand how to scale this project for bigger businesses

## 📁 Overall Project Structure

**How to use this project:**

- Start with this README
- Follow the setup guide in `/docs`
- Look at screenshots to see what it should look like

---
