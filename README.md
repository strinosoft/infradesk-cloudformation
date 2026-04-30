# GetInfraDesk — CloudFormation IAM Role

Public CloudFormation template for GetInfraDesk AWS Cost Optimization.

## What this creates

A secure IAM role in your AWS account that GetInfraDesk uses for read-only cost scanning and safe remediation.

## Deploy

[![Launch Stack](https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png)](https://console.aws.amazon.com/cloudformation/home#/stacks/create/review?templateURL=https://infradesk-templates.s3.amazonaws.com/infradesk-role.json)

Or use this template URL directly:

https://infradesk-templates.s3.amazonaws.com/infradesk-role.json

## Security

- Read-only by default
- Write permissions only used with your explicit approval
- Production resources protected by tag-based deny policy
- Every action logged in GetInfraDesk Decision Log

See [permissions-explained.md](./permissions-explained.md) for full breakdown.

## Product

**getinfradesk.com** — Cut AWS waste safely. Prove every dollar saved.
