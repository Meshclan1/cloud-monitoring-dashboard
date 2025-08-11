# 💰 Project Cost Breakdown

_Prior to commencing projects, I use the AWS Pricing Calculator! It isa great way to estimate costs before building anything - https://calculator.aws/#/_

**Monthly cost estimate table:**

| Service    | Usage                       | Cost/Month | Justification                     |
| ---------- | --------------------------- | ---------- | --------------------------------- |
| CloudWatch | 10 custom metrics, 5 alarms | £2.50      | Essential visibility              |
| SES        | 100 emails/month            | £0.10      | Alert notifications               |
| SNS        | 100 notifications           | £0.05      | Message routing                   |
| **Total**  |                             | **£2.65**  | Well within small business budget |

## 💵 Cost Optimisation Strategies

**Used Free Tier Services**

- Basic CloudWatch metrics (CPU, memory, network) are free
- First 10 CloudWatch alarms are free
- SES gives you 62,000 emails/month free if sent from EC2

**Limited Custom Metrics**

- Only monitor essential things: CPU, memory, disk, cost
- Didn't add fancy business metrics (would cost £0.50 each per month)

**Smart Alert Settings**

- Set alerts to trigger only for real problems
- This reduces SNS message costs

**Simple Dashboard**

- Used basic CloudWatch dashboards (free)
- Didn't use third-party dashboard tools
- Delete alarms/dashboards not in use

## 🧐 Scaling Cost Projections

### 1 Server (Starting Out)

- Total: ~£2.65/month
- Perfect for testing and small websites

### 3-5 Servers (Growing Business)

- CloudWatch alarms: £10-15/month (more alarms needed)
- Total: ~£12-18/month
- Still very affordable

### 10+ Servers (Established Business)

- CloudWatch costs: £30-50/month
- Total: ~£35-55/month

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
- **High-frequency alarms**: Checking every minute vs every 5 minutes
- **Detailed monitoring**: Costs extra for EC2 instances

---
