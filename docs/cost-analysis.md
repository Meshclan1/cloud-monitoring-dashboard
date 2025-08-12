# 💵 Cost Analysis

This project is designed to stay within AWS Free Tier limits for small deployments.

---

## 📊 Service Costs

| Service              | Usage                      | Cost/Month | Justification                 |
| -------------------- | -------------------------- | ---------- | ----------------------------- |
| EC2 Instance         | t2.micro or t3.micro       | £7–12      | Server to monitor (main cost) |
| CloudWatch Basic     | CPU, network, disk metrics | £0         | Free basic EC2 metrics        |
| CloudWatch Alarms    | 3–5 alarms                 | £0         | First 10 alarms are free      |
| SES                  | 50 emails/month            | £0         | Under 62,000 free limit       |
| SNS                  | 50 notifications           | £0         | Under 1 million free limit    |
| **Total (1 server)** |                            | **£7–12**  | Realistic small business cost |

---

## 📈 Scaling Cost Projections

### Server Costs (Compute Only) 💻

| Number of Servers | EC2 Cost/Month (Estimate) | Notes                |
| ----------------- | ------------------------- | -------------------- |
| 1                 | £7–12                     | t2.micro or t3.micro |
| 3                 | £21–36                    | 3 × instances        |
| 5                 | £35–60                    |                      |
| 10                | £70–120                   |                      |
| 20                | £140–240                  |                      |

---

### Monitoring Costs 🔍

| Number of Servers | Monitoring Cost Estimate | Notes                                        |
| ----------------- | ------------------------ | -------------------------------------------- |
| 1–5               | £0–8                     | Mostly free tier, some custom metrics        |
| 10                | £50–170                  | Custom metrics & many alarms                 |
| 20+               | £200+                    | High CloudWatch usage, consider alternatives |

---

### Total Monthly Cost Estimate (Server + Monitoring) 💰

| Number of Servers | Total Cost Estimate | Notes                              |
| ----------------- | ------------------- | ---------------------------------- |
| 1                 | £7–20               | Single server + basic monitoring   |
| 5                 | £35–68              | 5 servers + light monitoring       |
| 10                | £120–290            | 10 servers + advanced monitoring   |
| 20                | £340+               | Larger infrastructure + monitoring |

---

### Notes:

- Each EC2 instance adds roughly £7–12/month regardless of monitoring.
- Monitoring costs start small but can grow significantly with custom metrics and alarms.
- For 20+ servers, consider cost-efficient or open-source monitoring tools.
