**sxo\_aws\_ir - Incident Response for EC2 in AWS**

This workflow simplifies and automates incident response procedures for Amazon EC2 instances. If a compromise is suspected, the workflow can automate incident response procedures that are detailed in the published [Amazon AWS Incident Response Guide](https://docs.aws.amazon.com/whitepapers/latest/aws-security-incident-response-guide/aws-security-incident-response-guide.pdf), including:

* Enabling Termination Proctection
* Moving the compromised instance to an isolated security group.
* Removing the instance from auto-scaling groups (ASGs).
* Removing the instance from an elastic load balancer (ELB).
* Creating forensic snapshots of elastic block devices.
* Adding tags to compromised hosts. 

## Required Targets

* Amazon Web Services

## Required Local Variables
* Isolation Security Group ID
* Target ELB ARN

## Setup instructions

Browse to your SecureX orchestration instance. This will be a different URL depending on the region your account is in:

* US: https://securex-ao.us.security.cisco.com/orch-ui/workflows/
* EU: https://securex-ao.eu.security.cisco.com/orch-ui/workflows/
* APJC: https://securex-ao.apjc.security.cisco.com/orch-ui/workflows/

### Import main workflow

1. In the left pane menu, select Workflows. Click on IMPORT to import the workflow.

2. Click on Browse and copy paste the content of the name-json-file.json file inside of the text window. Select IMPORT AS A NEW WORKFLOW (CLONE) and click on IMPORT.

3. Next steps, like updating targets / account keys and setting a trigger / running the workflow.

### Update local variables, targets, and credentials

This workflow relies on details from your AWS environment including authentication, region, quarantine security group, and ELB detail.

## Workflow

<img src="https://github.com/briansak/sxo_aws_ir/blob/main/img/workflow.png" width="400" height="1770">

### Notes
Please test this properly before implementing in a production environment. This is a sample workflow!
In a future version web hooks will be added to trigger the workflow rather than running it on a schedule or manually.
