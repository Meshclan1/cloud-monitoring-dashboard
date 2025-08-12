# 🏗️ Architecture & Flow

## 📜 Business Context

```
Small businesses often lack affordable monitoring solutions. This project uses AWS services to provide operational visibility with minimal cost.
```

---

## 🔍 Tech Stack

**What each part does:**

1. **Amazon EC2 Instance** – Runs the server/application you want to monitor
2. **Amazon CloudWatch** – Collects CPU, network, and disk metrics automatically
3. **Amazon CloudWatch Alarms** – Triggers notifications when thresholds are exceeded
4. **Amazon SNS** – Sends messages to subscribed recipients
5. **Amazon SES** – Sends alert emails

---

## 🔄 Architectural Data Flow

1. **Metrics Collection** – EC2 sends CPU, network, and disk data to CloudWatch
2. **Monitoring** – CloudWatch dashboard displays metrics
3. **Alert Trigger** – Alarms fire when thresholds are crossed
4. **Notification Delivery** – SNS sends a message; SES delivers an email

---

## 📊 Why This Architecture Works

- **Low cost:** Stays within AWS Free Tier for small workloads
- **Scalable:** Can expand to multiple servers with minimal changes
- **Reliable:** Uses AWS-native tools with built-in integration

---

## Key Design Decisions 🥸

### Decision 1: Use Native AWS Services

- **What I decided:** Only use AWS services, no third-party tools
- **Why:** Easier to set up, cheaper, everything works together

### Decision 2: Email Alerts Only

- **What I decided:** Just email notifications for now
- **Why:** Everyone checks email, no need to learn new tools

### Decision 3: Basic Metrics Only

- **What I decided:** Monitor CPU, memory, disk, cost - that's it
- **Why:** These catch most problems, and they're mostly free

### Decision 4: Simple Thresholds

- **What I decided:** Alert when CPU > 80% for 5 minutes
- **Why:** Catches real problems without too many false alarms

---

## 🖼️ Example Diagram

![Architecture Diagram](/docs/images/cloud-monitor-architecture.png)  
_Diagram showing EC2 → CloudWatch → SNS/SES alerting flow._
