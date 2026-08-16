# Project 8: AWS IAM Billing Access

## Objective

Create a dedicated **Finance IAM user/group** with read-only access to AWS Billing and Cost Management information.

The goal of this project is to understand how IAM permissions can be used to provide controlled access to billing information without giving unnecessary administrative permissions.

## Project Overview

In this project, I created a Finance IAM group/user and provided the required permissions to view AWS billing and cost information.

The IAM user was able to access the **Billing and Cost Management** console and view billing information while maintaining restricted access to other AWS resources.

## AWS Services Used

* AWS IAM
* AWS Billing and Cost Management
* AWS Management Console

## Architecture

```text
                AWS Account
                    │
                    ▼
              Finance IAM User
                    │
                    ▼
              Finance IAM Group
                    │
                    ▼
          Billing Read-Only Permissions
                    │
                    ▼
       AWS Billing & Cost Management
```

## Project Scenario

A company wants its finance team to view AWS billing information without giving them full administrator permissions.

To achieve this requirement:

```text
Finance User
     ↓
Finance Group
     ↓
Billing Read-Only Permissions
     ↓
View Billing Information
```

This follows the **principle of least privilege**.

## Implementation Steps

### Step 1: Open AWS IAM

1. Logged in to the AWS Management Console.
2. Opened **IAM**.
3. Navigated to **User groups**.

### Step 2: Create Finance Group

Created an IAM group named:

```text id="y6j4j8"
Finance
```

The group is used to manage permissions for finance-related users.

### Step 3: Add Billing Permissions

Attached the required billing-related read-only permissions to the Finance group.

The permissions allow the user to view billing and cost information without granting unnecessary administrative access.

### Step 4: Create Finance IAM User

Created an IAM user for the finance team.

The user was added to the:

```text id="gj6u8f"
Finance
```

IAM group.

### Step 5: Sign In as Finance User

Signed in using the Finance IAM user's credentials.

The user was able to access the AWS Billing and Cost Management console.

### Step 6: Verify Billing Access

Opened:

```text id="xoq1a3"
Billing and Cost Management
```

Verified that the Finance user could view the available billing information.

## Verification

The Finance IAM user was tested after the permissions were assigned.

### Expected Result

```text
Finance IAM User
       ↓
Finance IAM Group
       ↓
Billing Read-Only Permissions
       ↓
View Billing Information
```

The user was able to view billing information without requiring full administrator permissions.

## Security Concept

The project demonstrates **least-privilege access**.

Instead of giving the Finance user:

```text id="w1xxj5"
AdministratorAccess
```

only the permissions required for billing-related tasks were provided.

This reduces the risk of accidental or unauthorized changes to AWS resources.

## Benefits

* Provides controlled billing access.
* Separates finance responsibilities from technical administration.
* Reduces unnecessary permissions.
* Supports the principle of least privilege.
* Improves AWS account security.
* Makes permission management easier through IAM groups.

## Security Best Practices

* Use IAM groups to manage permissions for users with similar responsibilities.
* Grant only the permissions required for the job.
* Avoid giving finance users full administrator access.
* Enable MFA for IAM users.
* Regularly review IAM permissions.
* Never share passwords or AWS credentials.
* Never upload AWS credentials to GitHub.

## Learning Outcomes

Through this project, I learned:

* AWS IAM Groups
* IAM Users
* Billing and Cost Management access
* Billing permissions
* Read-only access
* IAM permission management
* Principle of Least Privilege
* AWS account security
* Role-based permission management

## Screenshots

The `screenshots` folder contains evidence of:

1. Finance IAM group creation
2. Billing permissions attached to the group
3. Finance IAM user
4. Finance user added to the group
5. Billing and Cost Management console
6. Successful billing access verification

> **Security Note:** Never upload AWS passwords, Access Keys, Secret Access Keys, MFA secrets, recovery codes, or other sensitive information to GitHub.

## Project Result

Successfully created a **Finance IAM user/group** with controlled access to AWS Billing and Cost Management information.

The Finance user was able to view billing information without being given unnecessary administrative permissions.

## Conclusion

This project demonstrated how AWS IAM can be used to provide department-specific access to AWS services.

By creating a dedicated Finance group and assigning billing-related permissions, the project implemented controlled access while following the principle of least privilege.

### Key Concept

> **Finance User → Finance Group → Billing Read-Only Permissions → AWS Billing**
