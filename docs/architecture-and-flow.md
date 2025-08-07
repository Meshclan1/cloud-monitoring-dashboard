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

```

```

```

```

## Key Design Decisions

### Decision 1:

- **What I decided:**
- **Why:**

### Decision 2:

- **What I decided:**
- **Why:**

---
