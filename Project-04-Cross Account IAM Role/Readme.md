# Project 4: AWS IAM Password Policy

## Objective

Configure a strong **AWS IAM Password Policy** to improve the security of IAM users and prevent the use of weak passwords.

## Project Overview

In this project, I configured an AWS IAM password policy with strong password requirements.

The policy requires IAM users to create passwords that meet specific security requirements, including minimum length, uppercase letters, lowercase letters, numbers, and special characters.

Password reuse prevention was also enabled to improve account security.

## AWS Services Used

* AWS IAM
* AWS Management Console

## Password Policy Configuration

The following security requirements were configured:

| Security Requirement       | Configuration |
| -------------------------- | ------------- |
| Minimum Password Length    | 14 characters |
| Require Uppercase Letters  | Enabled       |
| Require Lowercase Letters  | Enabled       |
| Require Numbers            | Enabled       |
| Require Special Characters | Enabled       |
| Password Reuse Prevention  | Enabled       |

## Architecture

```text
                 AWS IAM
                    │
                    ▼
           ┌─────────────────┐
           │ Password Policy │
           └────────┬────────┘
                    │
       ┌────────────┼────────────┐
       ▼            ▼            ▼
  14 Characters  Complexity  Reuse Prevention
       │            │            │
       └────────────┼────────────┘
                    ▼
              Strong Password
                    │
                    ▼
                IAM Users
```

## Implementation Steps

### Step 1: Open AWS IAM

1. Logged in to the AWS Management Console.
2. Opened **IAM**.
3. Navigated to **Account settings**.
4. Located the **Password policy** section.

### Step 2: Configure Minimum Password Length

Set the minimum password length to:

```text
14 characters
```

This prevents users from creating passwords that are too short.

### Step 3: Configure Password Complexity

Enabled the following requirements:

```text
✓ Require at least one uppercase letter
✓ Require at least one lowercase letter
✓ Require at least one number
✓ Require at least one non-alphanumeric character
```

### Step 4: Enable Password Reuse Prevention

Enabled password reuse prevention so that users cannot repeatedly reuse previously used passwords according to the configured policy.

### Step 5: Save the Password Policy

Reviewed all configured requirements and saved the password policy.

The AWS IAM password policy was successfully updated.

## Password Requirements

An IAM user password must satisfy the configured requirements:

```text
Minimum Length       : 14 characters
Uppercase            : Required
Lowercase            : Required
Number               : Required
Special Character    : Required
Password Reuse       : Prevented
```

Example of a strong password format:

```text
StrongPassword@2026
```

> **Note:** This is only an example. Never use this example as an actual AWS password.

## Verification

After configuring the policy, the password requirements were verified from the AWS IAM account settings.

The configured policy successfully enforced the required password complexity.

### Expected Result

```text
14+ Characters
      +
Uppercase
      +
Lowercase
      +
Number
      +
Special Character
      +
Password Reuse Prevention
      ↓
Stronger IAM Password Security
```

## Security Benefits

A strong password policy helps to:

* Reduce weak passwords.
* Make password guessing more difficult.
* Improve IAM user security.
* Reduce the risk of unauthorized access.
* Prevent repeated password reuse.
* Establish consistent password requirements.

## Security Best Practices

* Use strong and unique passwords.
* Enable MFA for IAM users.
* Follow the principle of least privilege.
* Never share AWS passwords or credentials.
* Never upload passwords or credentials to GitHub.
* Avoid using the root user for everyday AWS activities.
* Regularly review IAM security settings.

## Learning Outcomes

Through this project, I learned:

* AWS IAM Password Policies
* IAM User Security
* Password Complexity Requirements
* Minimum Password Length
* Password Reuse Prevention
* AWS Authentication Security
* IAM Security Best Practices
* Principle of Least Privilege

## Screenshots

The `screenshots` folder contains evidence of:

1. AWS IAM Account Settings
2. Password Policy section
3. Minimum password length configuration
4. Uppercase, lowercase, number, and special character requirements
5. Password reuse prevention configuration
6. Successfully saved password policy

> **Security Note:** Never upload passwords, AWS Access Keys, Secret Access Keys, MFA secret keys, QR codes, or recovery codes to GitHub.

## Project Result

Successfully configured an **AWS IAM Password Policy** with:

* Minimum **14-character** passwords
* Uppercase letter requirement
* Lowercase letter requirement
* Number requirement
* Special character requirement
* Password reuse prevention

## Conclusion

This project demonstrated how AWS IAM Password Policies can be used to enforce strong password requirements and improve the security of IAM users.

By enforcing password complexity and preventing password reuse, the risk of weak credentials and unauthorized access can be reduced.

### Key Concept

> **Strong Password Policy + MFA + Least Privilege = Better AWS Security**
