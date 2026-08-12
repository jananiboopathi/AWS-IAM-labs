# Project 2: Custom IAM Policy Using AWS IAM

## Objective

Create and configure a custom IAM policy in AWS to provide specific permissions to an IAM user while following the principle of least privilege.

## Project Overview

In this project, I created a **custom IAM policy** instead of using a predefined AWS managed policy.

The policy provides controlled access to Amazon EC2 resources and demonstrates how permissions can be customized according to specific requirements.

## AWS Services Used

* AWS IAM
* Amazon EC2
* AWS Management Console

## Architecture

```text
IAM User
    ↓
Custom IAM Policy
    ↓
Specific EC2 Permissions
    ↓
Amazon EC2
```

## Implementation Steps

### Step 1: Open AWS IAM

1. Logged in to the AWS Management Console.
2. Opened **IAM**.
3. Navigated to **Policies**.

### Step 2: Create Custom IAM Policy

Created a new customer-managed policy using the JSON policy editor.

The policy was configured with specific EC2 permissions rather than granting full administrative access.

### Step 3: Configure Permissions

The custom policy allows selected EC2 actions required for the project.

Example permissions include:

```text
ec2:DescribeInstances
ec2:StartInstances
ec2:StopInstances
```

The permissions were restricted to the required AWS service instead of using unrestricted access.

### Step 4: Create the Policy

After reviewing the policy configuration, the custom policy was created successfully.

### Step 5: Attach the Policy

The custom policy was attached to the required IAM user.

### Step 6: Test the Permissions

Logged in using the IAM user and tested the assigned EC2 permissions.

The user was able to perform the actions allowed by the custom policy.

Actions outside the allowed permissions were restricted.

## Permission Concept

A custom IAM policy follows the principle of **least privilege**.

Instead of giving a user:

```text
AdministratorAccess
```

only the permissions required for the user's task are provided.

## Example Policy Structure

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeInstances",
        "ec2:StartInstances",
        "ec2:StopInstances"
      ],
      "Resource": "*"
    }
  ]
}
```

> Note: The exact permissions used in the AWS account may differ depending on the project configuration.

## Verification

The IAM user was tested after attaching the custom policy.

### Allowed Actions

* View EC2 instances
* Start EC2 instances
* Stop EC2 instances

### Restricted Actions

Actions not included in the custom policy are not permitted.

This demonstrates how IAM policies control access to AWS resources.

## Security Best Practice

The **principle of least privilege** should always be followed when creating IAM policies.

Users should receive only the permissions they need to perform their assigned tasks.

Avoid using:

```text
AdministratorAccess
```

when more limited permissions are sufficient.

## Learning Outcomes

Through this project, I learned:

* AWS IAM Policies
* Customer-managed IAM Policies
* IAM Permissions
* IAM Users
* EC2 Permissions
* JSON Policy Structure
* Allow and Deny concepts
* Principle of Least Privilege
* AWS Access Control
* IAM Security Best Practices

## Screenshots

The `screenshots` folder contains evidence of:

1. Custom IAM policy creation
2. Policy JSON configuration
3. Policy permissions
4. Policy attachment
5. Permission verification/testing

## Project Result

Successfully created and configured a **custom IAM policy** to provide controlled EC2 access.

This project demonstrates how AWS IAM can be used to implement **secure, fine-grained access control** instead of providing unnecessary permissions.

## Conclusion

This project provided hands-on experience with AWS IAM custom policies and permission management. I learned how to define specific permissions using JSON and apply the principle of least privilege to improve AWS security.
