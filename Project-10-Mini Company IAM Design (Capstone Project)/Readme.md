# Project 10: IAM Role for AWS Lambda

## Objective

Create an **IAM Role for an AWS Lambda function** and provide only the permissions required for the Lambda function to access AWS resources.

The main goal is to understand how IAM Roles provide secure, temporary permissions to AWS services without using long-term Access Keys.

## Project Overview

In this project, I created an IAM Role that can be assumed by **AWS Lambda**.

The role was attached to a Lambda function and provided the required permissions.

This demonstrates how AWS services can securely access other AWS resources using IAM Roles.

## AWS Services Used

* AWS IAM
* AWS Lambda
* Amazon S3
* AWS Management Console

## Architecture

```text
                AWS Lambda
                    │
                    ▼
               IAM Role
                    │
                    ▼
             IAM Policy
                    │
                    ▼
             Amazon S3
```

## Project Scenario

A Lambda function needs to access an Amazon S3 bucket.

Instead of storing AWS Access Keys inside the Lambda function, an IAM Role is used.

```text
Lambda Function
      ↓
Assume IAM Role
      ↓
Temporary Credentials
      ↓
S3 Permissions
      ↓
S3 Bucket
```

This is a secure and recommended approach for AWS applications.

## Implementation Steps

### Step 1: Open AWS IAM

1. Logged in to the AWS Management Console.
2. Opened **IAM**.
3. Navigated to **Roles**.
4. Selected **Create role**.

### Step 2: Select Trusted Entity

Selected:

```text
Trusted Entity:
AWS Service
```

Selected the service:

```text
AWS Lambda
```

This allows Lambda functions to assume the IAM Role.

### Step 3: Attach Permissions

Attached the required S3 permission policy.

For testing, an appropriate read-only policy can be used:

```text
AmazonS3ReadOnlyAccess
```

This allows the Lambda function to read S3 resources without granting unnecessary write or delete permissions.

### Step 4: Name the IAM Role

Created a descriptive role name, for example:

```text
Lambda-S3-ReadOnly-Role
```

The role was then created successfully.

### Step 5: Create Lambda Function

1. Opened **AWS Lambda**.
2. Selected **Create function**.
3. Created a new Lambda function.
4. Configured the function to use the existing IAM Role.

### Step 6: Attach IAM Role to Lambda

Selected:

```text
Lambda-S3-ReadOnly-Role
```

as the execution role for the Lambda function.

### Step 7: Test the Lambda Function

The Lambda function was tested to verify that it could access the permitted S3 resources.

The function used the IAM Role to obtain temporary credentials automatically.

No AWS Access Keys were stored inside the Lambda function.

## Example Lambda Code

The following Python example lists S3 buckets:

```python
import boto3

def lambda_handler(event, context):
    s3 = boto3.client("s3")

    response = s3.list_buckets()

    buckets = [bucket["Name"] for bucket in response["Buckets"]]

    print("S3 Buckets:")
    for bucket in buckets:
        print(bucket)

    return {
        "statusCode": 200,
        "buckets": buckets
    }
```

## Authentication Method

### Insecure Approach ❌

Storing long-term credentials inside application code:

```text
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
```

This can expose sensitive credentials.

### IAM Role Approach ✅

```text
Lambda Function
      ↓
IAM Role
      ↓
Temporary Credentials
      ↓
Amazon S3
```

AWS automatically provides temporary credentials to the Lambda function through the execution role.

## Verification

The Lambda function was executed successfully.

The function was able to access the S3 resources allowed by the attached IAM policy.

### Expected Result

```text
Lambda Function
      ↓
Assume IAM Role
      ↓
Obtain Temporary Credentials
      ↓
Access S3
      ↓
Successful Response
```

## Security Benefits

Using an IAM Role for Lambda provides several security benefits:

* No long-term Access Keys are required.
* Temporary credentials are used.
* Permissions can be restricted.
* Access can be controlled using IAM policies.
* Credentials do not need to be stored in source code.
* Supports the principle of least privilege.

## Security Best Practices

* Use IAM Roles instead of Access Keys for Lambda.
* Grant only the permissions required by the function.
* Avoid `AdministratorAccess` for Lambda functions.
* Use read-only policies when write access is unnecessary.
* Regularly review Lambda execution roles.
* Never hard-code AWS credentials in Lambda code.
* Never upload AWS credentials to GitHub.
* Follow the principle of least privilege.

## Learning Outcomes

Through this project, I learned:

* AWS Lambda
* IAM Roles
* Lambda Execution Roles
* IAM Policies
* Temporary Credentials
* Lambda-to-S3 access
* AWS SDK (`boto3`)
* Secure AWS authentication
* Principle of Least Privilege
* AWS security best practices

## Screenshots

The `screenshots` folder contains evidence of:

1. IAM Role creation
2. Lambda trusted entity selection
3. S3 permissions attached to the role
4. IAM Role details
5. Lambda function creation
6. Lambda execution role configuration
7. Lambda function code
8. Successful Lambda test execution

> **Security Note:** Never upload AWS Access Keys, Secret Access Keys, passwords, MFA secrets, QR codes, or other sensitive credentials to GitHub.

## Project Result

Successfully created an **IAM Role for AWS Lambda** and configured the Lambda function to access Amazon S3 using temporary credentials.

No long-term AWS Access Keys were stored in the Lambda function.

## Conclusion

This project demonstrated how IAM Roles can securely provide permissions to AWS Lambda functions.

Instead of storing long-term credentials, the Lambda function uses an IAM execution role and temporary credentials to access AWS resources.

This approach improves security, reduces credential exposure, and follows AWS best practices.

### Key Concept

> **Lambda → IAM Execution Role → Temporary Credentials → S3**
