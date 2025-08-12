# 📊 Business Ops Monitoring Dashboard

```
A lightweight AWS-based monitoring solution for small businesses, providing real-time visibility of server health, alerts for issues, and simple dashboards — all while staying within (or close to) AWS Free Tier limits.
```

---

## 🎯 Project Overview

**Goal:** Give small businesses a cost-effective way to monitor key operational metrics without complex tooling.

**Core AWS Services Used:**

- **Amazon EC2** – Hosts the application/server
- **Amazon CloudWatch** – Collects and displays CPU, network, and disk metrics
- **Amazon CloudWatch Alarms** – Triggers notifications when thresholds are exceeded
- **Amazon Simple Notification Service (SNS)** – Sends alerts
- **Amazon Simple Email Service (SES)** – Delivers email alerts

---

## 🏗️ Architecture Overview

![Architecture Diagram Placeholder](docs/images/architecture-placeholder.png)  
_Diagram showing EC2 → CloudWatch → SNS/SES alerting flow._

[📄 View full architecture details](docs/architecture-and-flow.md)

---

## 🚀 Setup Instructions

Follow the step-by-step AWS setup guide to deploy your own dashboard.

[📄 AWS Setup Guide](docs/aws-setup-guide.md)

---

## 💵 Cost Considerations

This project is designed to be affordable for learning and small business use.

[📄 View Cost Analysis](docs/cost-analysis.md)

---

## 📌 Features

- 📉 **Real-time metrics:** CPU, network, and disk
- 🚨 **Custom alarms:** Trigger only on real operational issues
- ✉️ **Email notifications:** Receive alerts directly in your inbox
- 🆓 **Free tier friendly:** Keep monthly costs near £0 for small workloads

---

## 🔮 Future Improvements

- Add memory and application-level metrics
- Including an alarm description for formatting purposes
- See how I can connect and showcase the dashboard via the web using a python module or using javascript libraries/frameworks
- Configure automatic actions to problems to reduce manual intervention (e.g. Lambda, Auto-Scaling, EC2 action)
- Create a cloud template for chosen IDE (VSCode). (Helps make building projects from scratch quicker!)
- Employ IaC via CloudFormation for quicker deployments
- Run tests at each step to ensure things are working properly

---

## 🧠 Lessons Learned

- Cost planning is as important as technical setup
- Simplicity keeps maintenance low
- Documentation is important!
- Taking screenshots at verification points (moments that prove each step worked correctly!)
- Regional selection affects both cost and latency
- Correctly using the AWS price calculator to estimate project costs

---

## 📂 Documentation

- [Architecture & Flow](docs/architecture-and-flow.md)
- [AWS Setup Guide](docs/aws-setup-guide.md)
- [Cost Analysis](docs/cost-analysis.md)
