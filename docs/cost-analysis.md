# 💰 Project Cost Breakdown

_Prior to commencing projects, I use the AWS Pricing Calculator! It isa great way to estimate costs before building anything - https://calculator.aws/#/_

**Monthly cost estimate table:**

Cost Estimates per month for EU-WEST-2 (London)

| Service          | Usage                                                | Cost/Month | Justification                                  |
| ---------------- | ---------------------------------------------------- | ---------- | ---------------------------------------------- |
| CloudWatch Basic | CPU, Network, Disk metrics, First 10 alarms are free | £2.50      | Essential visibility                           |
| SES              | 50 emails/month                                      | £0.00      | Alert notifications                            |
| SNS              | 50 notifications                                     | £0.00      | Message routing                                |
| **Total**        |                                                      | **£0.00**  | Optimal for small business with limited budget |

## 💵 Cost Optimisation Strategies

**Used Free Tier Services**

- Basic CloudWatch metrics (CPU, memory, network) are free
- First 10 CloudWatch alarms are free
- SES gives 62,000 emails/month free if sent from EC2

**Limited Custom Metrics**

- Only monitor essential things: CPU, memory, disk, cost
- Not adding business metrics (would cost £0.50 each per month)

**Smart Alert Settings**

- Set alerts to trigger only for real problems
- This reduces SNS message costs

**Simple Dashboard**

- Used basic CloudWatch dashboards (free)
- Didn't use third-party dashboard tools
- Delete alarms/dashboards not in use

## 🧐 Scaling Cost Projections

### 1 Server (Starting Out)

Basic monitoring: £0/month (always-free tiers)
Perfect for testing and small websites

### 3-5 Servers (Growing Business)

Basic monitoring: £0/month (still within free limits)
IF you add custom metrics (disk usage): £1-3/month
IF you need >10 alarms: £2-5/month additional
Total: £0-8/month - Still very affordable

### 10+ Servers (Established Business)

Basic monitoring: £0/month (free tier per server)
Custom metrics become expensive: £5-15/month per server
Many alarms needed: £10-20/month
Total: £50-170/month for comprehensive monitoring

### 20+ Servers (Enterprise Scale)

AWS CloudWatch becomes expensive: £200+/month
Recommendation: Switch to open-source solutions
Or use enterprise monitoring tools that become cost-effective at scale

### When to Switch Solutions

- **Stay with this setup**: Under 10 servers, basic monitoring needs
- **Consider alternatives**: 20+ servers, need advanced features

## 🔍 Cost Monitoring

### What I Set Up

- **Budget Alert**: Email when monthly spend hits £10
- **Weekly Cost Review**: Check billing dashboard every Friday
- **Cost Dashboard Widget**: Added billing metrics to main dashboard

### Red Flags to Watch For

- **CloudWatch custom metrics**: Each one costs £0.50/month
- **High-frequency alarms**: Checking every minute (high-resolution) vs every 5 minutes (standard)
- **Detailed monitoring**: Costs extra for EC2 instances

---
