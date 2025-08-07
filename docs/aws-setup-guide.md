# AWS Setup Guide

# Section 1: Prerequisites 📝

**What you need:**

- AWS account (free tier is fine)
- Email address for receiving alerts
- 30-60 minutes of time
- Basic AWS console knowledge (can navigate and click buttons)

**Permissions needed:**

- Access to CloudWatch, SES, SNS services
- If you're not the account owner, ask for these permissions

**Cost warning:** This setup uses mostly free services, but check your billing dashboard after setup.

# Section 2: Step-by-Step Setup 📕

## Step 1: Set Up Email (SES)

**Time needed: 5 minutes**

### What you're doing

Setting up AWS to send you alert emails.

### Steps

1. Go to AWS Console → Search "SES" → Click Simple Email Service
2. Click "Verified identities" on the left menu
3. Click "Create identity"
4. Choose "Email address"
5. Enter your email address → Click "Create identity"
6. **Go check your email** → Click the verification link
7. Come back to AWS → Your email should show "Verified"

### How to know it worked

Your email shows green checkmark and says "Verified"

### If it doesn't work

- Check spam folder for verification email
- Make sure you typed email correctly
- Try a different email address

## Step 2: Create Notification Topic (SNS)

**Time needed: 5 minutes**

### What you're doing

Creating a "topic" that will send messages to your email.

### Steps

1. Go to AWS Console → Search "SNS" → Click Simple Notification Service
2. Click "Topics" on left menu
3. Click "Create topic"
4. Choose "Standard" type
5. Name: "monitoring-alerts"
6. Click "Create topic"
7. Click "Create subscription"
8. Protocol: Choose "Email"
9. Endpoint: Enter your verified email
10. Click "Create subscription"
11. **Check your email again** → Click confirm subscription

### How to know it worked

Subscription shows "Confirmed" status

## Step 3: Create CloudWatch Dashboard

**Time needed: 15 minutes**

### What you're doing

Creating a page where you can see all your server metrics.

### Steps

1. Go to AWS Console → Search "CloudWatch" → Click CloudWatch
2. Click "Dashboards" on left menu
3. Click "Create dashboard"
4. Name: "My-Server-Monitoring"
5. Click "Create dashboard"

### Add CPU Monitoring Widget

1. Click "Add widget"
2. Choose "Line" chart
3. Choose "EC2" → "Per-Instance Metrics"
4. Find your server → Check "CPUUtilization"
5. Click "Create widget"

### Add More Widgets (repeat for each)

- Memory usage (if CloudWatch agent installed)
- Disk usage
- Network in/out

### Save Your Dashboard

Click "Save dashboard"

## Step 4: Create Alarms

**Time needed: 10 minutes each alarm**

### Create High CPU Alarm

1. In CloudWatch → Click "Alarms" → "All alarms"
2. Click "Create alarm"
3. Click "Select metric"
4. Choose "EC2" → "Per-Instance Metrics"
5. Find your server → Select "CPUUtilization"
6. Click "Select metric"
7. **Set up the alarm:**
   - Threshold: Static
   - Greater than: 80
   - Period: 5 minutes
   - Datapoints to alarm: 1 out of 1
8. Click "Next"
9. **Set up notifications:**
   - Alarm state: In alarm
   - SNS topic: Select your "monitoring-alerts" topic
10. Click "Next"
11. Name: "High-CPU-Alert"
12. Description: "CPU usage too high"
13. Click "Next" → "Create alarm"

### Test Your Alarm

1. Go to your alarm
2. Click "Actions" → "Set alarm state"
3. Choose "In alarm"
4. Check your email - you should get an alert!
5. Set it back to "OK" when done testing

## Step 5: Create Cost Alert

**Time needed: 5 minutes**

### What you're doing

Get notified if your AWS bill gets too high.

### Steps

1. Go to AWS Console → Search "Billing" → Billing and Cost Management
2. Click "Budgets" on left menu
3. Click "Create budget"
4. Choose "Use a template"
5. Select "Monthly cost budget"
6. Budget name: "Monthly-AWS-Budget"
7. Enter amount: £10 (or whatever you want)
8. Enter your email
9. Click "Create budget"

### How to know it worked

You'll see your budget listed and get an email confirmation.

# Section 3: Testing & Troubleshooting 📖

## Testing Your Setup

### Test 1: Check Dashboard

1. Go to CloudWatch → Dashboards → Your dashboard
2. You should see charts with data
3. If no data: Wait 5-10 minutes, then refresh

### Test 2: Test Email Alerts

1. Go to CloudWatch → Alarms
2. Find your CPU alarm
3. Actions → Set alarm state → "In alarm"
4. Check email within 2 minutes
5. Set alarm back to "OK"

### Test 3: Check Cost Monitoring

1. Billing → Budgets
2. Your budget should show current spend
3. If it shows £0.00, wait until tomorrow

## Troubleshooting

### No email alerts received

- Check spam folder
- Verify email is confirmed in SES
- Check SNS subscription is confirmed
- Test alarm manually as shown above

### Dashboard shows no data

- Wait 5-10 minutes for data to appear
- Check you selected the right EC2 instance
- Make sure your server is running

### Costs higher than expected

- Check CloudWatch pricing for custom metrics
- Review your alarm settings
- Consider reducing monitoring frequency

---
