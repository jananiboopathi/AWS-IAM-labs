# Project 3: EC2 Access S3 Without Access Keys

## Objective

Understand how **IAM Roles** allow an Amazon EC2 instance to securely access Amazon S3 without storing AWS Access Keys on the EC2 instance.

## Project Overview

In this project, I configured an **IAM Role** for an EC2 instance and attached the `AmazonS3ReadOnlyAccess` policy.

The EC2 instance was then able to access Amazon S3 using **temporary credentials provided automatically through the IAM Role**.

No long-term AWS Access Keys were stored on the EC2 instance.

## AWS Services Used

* Amazon EC2
* Amazon S3
* AWS IAM
* IAM Role
* AWS CLI

## Architecture

```text
                    AWS Cloud
                       │
                       ▼
                ┌─────────────┐
                │ EC2 Instance│
                └──────┬──────┘
                       │
                       ▼
                ┌─────────────┐
                │  IAM Role   │
                └──────┬──────┘
                       │
                       ▼
           AmazonS3ReadOnlyAccess
                       │
                       ▼
                ┌─────────────┐
                │  S3 Bucket  │
                └─────────────┘
```

## Implementation Steps

### Step 1: Create an IAM Role

Created an IAM Role for the EC2 service.

Trusted entity:

```text
AWS Service → EC2
```

This allows the EC2 instance to assume the IAM Role.

### Step 2: Attach S3 Read-Only Permission

Attached the AWS managed policy:

```text
AmazonS3ReadOnlyAccess
```

This policy provides read-only access to Amazon S3.

### Step 3: Launch EC2 Instance

Launched an EC2 instance and attached the IAM Role to the instance.

The role allows the EC2 instance to communicate with AWS services securely.

### Step 4: Connect to EC2

Connected to the EC2 instance using SSH.

The AWS CLI was available on the instance for testing AWS service access.

### Step 5: Verify IAM Role

Verified that the EC2 instance could use the IAM Role to obtain temporary credentials.

No AWS Access Key ID or Secret Access Key was manually configured.

### Step 6: Test S3 Access

Executed the following command:

```bash
aws s3 ls
```

The command successfully listed the available S3 buckets.

## Verification

### Command

```bash
aws s3 ls
```

### Result

The S3 buckets were successfully displayed.

This confirms that the EC2 instance has permission to access S3 through the attached IAM Role.

## Authentication Method

### Traditional Method ❌

An application could be configured with long-term credentials:

```text
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
```

Storing these credentials on an EC2 instance creates a security risk.

### IAM Role Method ✅

With an IAM Role:

```text
EC2 Instance
      ↓
IAM Role
      ↓
Temporary Credentials
      ↓
Amazon S3
```

AWS automatically provides temporary credentials to the EC2 instance.

No long-term access keys are required.

## Security Best Practices

* Use IAM Roles for EC2 applications.
* Avoid storing AWS Access Keys on EC2 instances.
* Follow the principle of least privilege.
* Use only the permissions required by the application.
* Prefer temporary credentials over long-term credentials.
* Regularly review IAM permissions.

## Learning Outcomes

Through this project, I learned:

* IAM Roles
* IAM Policies
* EC2 Instance Roles
* Temporary Credentials
* Amazon S3 Access
* AWS CLI
* EC2 to S3 communication
* Secure AWS authentication
* Principle of Least Privilege
* AWS Security Best Practices

## Screenshots

The `screenshots` folder contains evidence of:

1. IAM Role creation
2. `AmazonS3ReadOnlyAccess` policy attachment
3. IAM Role attached to EC2
4. S3 bucket configuration
5. EC2 terminal
6. Successful `aws s3 ls` command

## Project Result

Successfully configured an **EC2 instance to access Amazon S3 without using or storing AWS Access Keys**.

The EC2 instance accessed S3 using an **IAM Role and temporary credentials**.

## Conclusion

This project demonstrated the secure way to allow an EC2 instance to access AWS services.

By using an IAM Role instead of long-term Access Keys, AWS applications can access resources securely through temporary credentials. This reduces the risk of credential exposure and follows AWS security best practices.

### Key Concept

> **EC2 → IAM Role → Temporary Credentials → S3**

This project strengthened my understanding of **AWS IAM Roles, temporary credentials, EC2, S3, and secure cloud access management**.
