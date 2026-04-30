# GetInfraDesk — IAM Permissions Explained

Every permission GetInfraDesk requests is listed here with a clear explanation of why it's needed.

**Our promise:** Read-only by default. Write permissions are only used when you explicitly approve a fix.

---

## EC2 Permissions

| Permission | Type | Why We Need It |
|-----------|------|----------------|
| `ec2:DescribeInstances` | Read | Detect stopped/idle EC2 instances |
| `ec2:DescribeVolumes` | Read | Find unattached EBS volumes |
| `ec2:DescribeAddresses` | Read | Find orphan Elastic IPs |
| `ec2:DescribeRegions` | Read | Scan all active AWS regions |
| `ec2:StopInstances` | Write | Stop idle instances (only with your approval) |
| `ec2:StartInstances` | Write | Restart instances (rollback) |

## RDS Permissions

| Permission | Type | Why We Need It |
|-----------|------|----------------|
| `rds:DescribeDBInstances` | Read | Detect idle/oversized RDS instances |
| `rds:DescribeDBClusters` | Read | Detect idle Aurora clusters |
| `rds:StopDBInstance` | Write | Stop idle RDS (only with your approval) |
| `rds:StartDBInstance` | Write | Restart RDS (rollback) |

## Cost & Billing Permissions

| Permission | Type | Why We Need It |
|-----------|------|----------------|
| `ce:GetCostAndUsage` | Read | Fetch real AWS cost data |
| `ce:GetCostForecast` | Read | Show monthly spend forecast |
| `ce:GetAnomalyMonitors` | Read | Detect cost anomalies |
| `ce:GetSavingsPlansPurchaseRecommendation` | Read | RI/SP optimization suggestions |

## CloudWatch Permissions

| Permission | Type | Why We Need It |
|-----------|------|----------------|
| `cloudwatch:GetMetricStatistics` | Read | CPU/memory usage for rightsizing |
| `cloudwatch:ListMetrics` | Read | Discover available metrics |
| `logs:DescribeLogGroups` | Read | Detect expensive log retention |

## AutoScaling Permissions

| Permission | Type | Why We Need It |
|-----------|------|----------------|
| `autoscaling:DescribeAutoScalingGroups` | Read | Detect controller-managed EC2 |
| `autoscaling:UpdateAutoScalingGroup` | Write | Fix at ASG level (not leaf EC2) |

## EKS Permissions

| Permission | Type | Why We Need It |
|-----------|------|----------------|
| `eks:ListClusters` | Read | Detect EKS clusters |
| `eks:DescribeCluster` | Read | Cluster cost visibility |

## IAM Permissions

| Permission | Type | Why We Need It |
|-----------|------|----------------|
| `sts:AssumeRole` | Write | Cross-account access via role |
| `iam:GetRole` | Read | Verify role exists |

---

## What We NEVER Do

- ❌ Never delete any resource without explicit approval
- ❌ Never modify production databases without approval
- ❌ Never store your AWS credentials
- ❌ Never share your data with third parties
- ✅ Every action is logged in Decision Log
- ✅ Every fix has a rollback option
- ✅ Read-only scan by default

---

## CloudFormation Template

The exact IAM role GetInfraDesk creates is in `infradesk-role.json` in this repo.

You can review every permission before deploying.

**Template URL:**
https://infradesk-templates.s3.amazonaws.com/infradesk-role.json
---

## Security Contact

Found a security issue? Email: security@getinfradesk.com

---

*GetInfraDesk — Cut AWS waste safely. Prove every dollar saved.*
*getinfradesk.com*
