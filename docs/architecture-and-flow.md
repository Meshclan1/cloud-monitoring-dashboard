## Business Context

```
Small businesses using AWS don't know when their servers are having problems. They find out when customers can't access their website or when they get a huge AWS bill. This costs them money and customers.

This monitoring solution gives them a simple way to watch their servers and get alerts before problems become expensive.
```

## Solution Overview

**The Big Picture:**

- CloudWatch watches your servers and collects data
- When something goes wrong, CloudWatch creates an alarm
- The alarm sends a message through SNS
- SNS sends you an email through SES
- You can see everything on a dashboard

**Why These Services:**

- CloudWatch: Built into AWS, free for basic monitoring
- SNS: Reliable way to send messages between AWS services
- SES: Cheap email service (much cheaper than other options)

## Architecture Details

**What Each Part Does:**

- **EC2 Server**: Your website/application server
- **CloudWatch**: Collects data (CPU, memory, etc.)
- **Alarm**: Triggers when something is wrong
- **SNS**: Routes the alert message
- **SES**: Sends you an email
- **Dashboard**: Where you check everything is OK

**Layer Breakdown:**

- **Monitoring Layer**: CloudWatch metrics, custom metrics, logs
- **Alerting Layer**: CloudWatch alarms, SNS topics, SES configuration
- **Presentation Layer**: CloudWatch dashboards, mobile access
- **Security Layer**: IAM roles, least privilege access

### Simple Components Diagram

```
diagram here
```

## Data Flow Through the System

### Normal Operation (Everything OK)

1. Your EC2 server runs normally
2. CloudWatch collects metrics every 5 minutes
3. You can check the dashboard anytime
4. No alerts sent

### When There's a Problem

1. Server CPU goes above 80% for 5 minutes
2. CloudWatch alarm triggers
3. Alarm sends message to SNS topic
4. SNS forwards message to SES
5. SES sends email to you
6. You get notified within 2 minutes

### What Data Gets Collected

- **CPU Usage**: How busy your server is
- **Memory Usage**: How much RAM is being used
- **Disk Space**: How full your hard drive is
- **Network**: Data going in and out
- **Cost**: How much you're spending on AWS

## Data Flow Through AWS System

### Normal Operation (Everything OK)

1.
2.

### When There's a Problem

1.
2.

### What Data Gets Collected

-
-

### Flow Chart for each Component Layer

**Normal Operations Flow**

```
EC2 → CloudWatch Agent → CloudWatch Metrics → Dashboard → User

```

**Alert Flow**

```
CloudWatch Alarm → SNS Topic → SES → Email → Business Owner

```

**Cost Monitoring Flow**

```
AWS Billing → CloudWatch Billing Metrics → Cost Alarm → Alert

```

## Key Design Decisions

### Decision 1: Use Native AWS Services

**What I decided:** Only use AWS services, no third-party tools
**Why:** Easier to set up, cheaper, everything works together

### Decision 2: Email Alerts Only

**What I decided:** Just email notifications for now
**Why:** Everyone checks email, no need to learn new tools

### Decision 3: Basic Metrics Only

**What I decided:** Monitor CPU, memory, disk, cost - that's it
**Why:** These catch most problems, and they're mostly free

### Decision 4: Simple Thresholds

**What I decided:** Alert when CPU > 80% for 5 minutes
**Why:** Catches real problems without too many false alarms

---
