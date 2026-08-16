# Project 9: AWS IAM Access Analyzer

## Objective

Use **AWS IAM Access Analyzer** to identify resources that are accessible from outside the AWS account and improve the security of AWS resource permissions.

## Project Overview

In this project, I used **IAM Access Analyzer** to analyze resource-based policies and identify resources that may be accessible by external principals.

IAM Access Analyzer helps identify unintended access and supports the principle of least privilege.

## AWS Services Used

* AWS IAM
* IAM Access Analyzer
* Amazon S3
* AWS Management Console

## Architecture

```text
                 AWS Account
                     │
                     ▼
             IAM Access Analyzer
                     │
                     ▼
            Analyze Resource Policies
                     │
          ┌──────────┴──────────┐
          ▼                     ▼
    No External Access    External Access
          │                     │
          ▼                     ▼
       Secure              Review Policy
                                │
                                ▼
                       Remove Unnecessary
                            Permissions
```

## Project Scenario

An organization wants to identify AWS resources that may be accessible by users or accounts outside the organization.

IAM Access Analyzer is used to analyze resource-based policies and identify possible external access.

The goal is to detect unintended permissions and improve AWS security.

## Implementation Steps

### Step 1: Open IAM Access Analyzer

1. Logged in to the AWS Management Console.
2. Opened **IAM**.
3. Navigated to **Access Analyzer**.

### Step 2: Create an Analyzer

Created an Access Analyzer for the AWS account.

The analyzer was configured to analyze resources within the AWS account and identify access granted to external principals.

### Step 3: Review Analyzer Findings

After creating the analyzer, reviewed the generated findings.

The analyzer checks supported AWS resources and identifies policies that grant access outside the intended trust boundary.

### Step 4: Analyze Findings

Reviewed each finding to understand:

* Which resource is accessible
* Who can access the resource
* What permissions are available
* Which policy grants the access

### Step 5: Review Resource Policy

Inspected the resource-based policy responsible for the identified access.

For example, an S3 bucket policy may accidentally allow access to an external AWS account.

### Step 6: Remediate Unnecessary Access

If external access was not required, the unnecessary permission was removed or restricted.

The resource policy was then reviewed again.

### Step 7: Verify the Configuration

Verified the Access Analyzer findings after making the required policy changes.

The purpose was to ensure that unintended external access was removed.

## Example Finding

An Access Analyzer finding may identify a resource with external access.

Example:

```text
Resource:
S3 Bucket

Access:
External AWS Account

Permission:
s3:GetObject

Status:
Needs Review
```

The finding should be investigated to determine whether the access is intentional.

## Verification

IAM Access Analyzer was used to identify and review resource access.

The analysis helped determine whether resources were accessible by external principals.

### Expected Workflow

```text
Create Analyzer
      ↓
Analyze Resources
      ↓
Generate Findings
      ↓
Review External Access
      ↓
Remove Unnecessary Access
      ↓
Verify Permissions
```

## Security Benefits

IAM Access Analyzer helps organizations:

* Identify unintended external access.
* Review resource-based policies.
* Detect overly permissive resource policies.
* Improve AWS security.
* Support least-privilege access.
* Reduce unnecessary external access.

## Security Best Practices

* Regularly review IAM Access Analyzer findings.
* Investigate unexpected external access.
* Follow the principle of least privilege.
* Avoid unnecessarily broad resource policies.
* Review S3 bucket policies carefully.
* Remove permissions that are no longer required.
* Use IAM groups and roles appropriately.
* Enable MFA for IAM users.
* Never upload AWS credentials to GitHub.

## Learning Outcomes

Through this project, I learned:

* AWS IAM Access Analyzer
* Resource-based policies
* External access
* IAM permissions
* S3 bucket policies
* Access Analyzer findings
* Permission analysis
* Security auditing
* Principle of Least Privilege
* AWS security best practices

## Screenshots

The `screenshots` folder contains evidence of:

1. IAM Access Analyzer page
2. Analyzer creation
3. Analyzer configuration
4. Generated findings
5. Finding details
6. Resource policy review
7. Updated security configuration

> **Security Note:** Never upload AWS passwords, Access Keys, Secret Access Keys, MFA secrets, QR codes, recovery codes, or other sensitive information to GitHub.

## Project Result

Successfully configured and used **AWS IAM Access Analyzer** to analyze resource access and identify potential external access.

The project demonstrated how Access Analyzer can help detect unintended permissions and improve AWS resource security.

## Conclusion

This project provided hands-on experience with AWS IAM Access Analyzer and resource-based policies.

IAM Access Analyzer is an important security tool for identifying resources that may be accessible outside the intended AWS account or organization.

By reviewing findings and removing unnecessary permissions, organizations can reduce security risks and follow the principle of least privilege.

### Key Concept

> **Analyze Access → Identify Findings → Review Permissions → Remove Unnecessary Access → Improve Security**
