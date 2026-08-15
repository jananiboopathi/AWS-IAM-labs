# Project 5: MFA Security in AWS IAM

## Objective

Implement **Multi-Factor Authentication (MFA)** in AWS IAM to provide an additional layer of security for AWS user accounts.

## Project Overview

In this project, I configured MFA for an AWS IAM user to strengthen account security.

MFA requires users to provide an additional authentication factor along with their password when signing in.

This helps protect AWS resources even if a user's password is compromised.

## AWS Services Used

* AWS IAM
* AWS Management Console
* Multi-Factor Authentication (MFA)

## Architecture

```text
                 User
                  │
                  ▼
          ┌───────────────┐
          │ Username +    │
          │ Password      │
          └───────┬───────┘
                  │
                  ▼
          ┌───────────────┐
          │     MFA       │
          │ Verification  │
          └───────┬───────┘
                  │
                  ▼
          AWS Management
              Console
                  │
                  ▼
          AWS Resources
```

## Implementation Steps

### Step 1: Open AWS IAM

1. Logged in to the AWS Management Console.
2. Opened **IAM**.
3. Navigated to **Users**.
4. Selected the required IAM user.

### Step 2: Configure MFA

Navigated to the user's **Security credentials** section.

Under **Multi-factor authentication (MFA)**, selected the option to assign an MFA device.

### Step 3: Select MFA Device

Configured a virtual MFA device using an authenticator application.

The authenticator application generates a time-based one-time password (TOTP).

### Step 4: Register the MFA Device

Scanned the QR code using the authenticator application.

Entered the generated MFA codes to complete device verification.

The MFA device was successfully assigned to the IAM user.

### Step 5: Test MFA Authentication

Signed in using the IAM user's credentials.

During authentication, AWS required the MFA verification code in addition to the password.

The user successfully authenticated after providing the correct MFA code.

## Security Concept

MFA provides an additional authentication factor.

Without MFA:

```text
Username + Password
        ↓
      Login
```

With MFA:

```text
Username + Password
        ↓
     MFA Code
        ↓
      Login
```

This provides stronger protection against unauthorized access.

## Benefits of MFA

* Provides an additional layer of security.
* Helps protect accounts if passwords are compromised.
* Reduces the risk of unauthorized access.
* Strengthens AWS account security.
* Supports AWS security best practices.

## Security Best Practices

* Enable MFA for IAM users where appropriate.
* Protect the authenticator device.
* Never share MFA codes with anyone.
* Use strong and unique passwords.
* Follow the principle of least privilege.
* Avoid using the root user for everyday AWS tasks.
* Enable MFA protection for the AWS root user.

## Verification

The MFA configuration was successfully verified by signing in with the IAM user and completing the MFA authentication step.

### Expected Result

```text
Password Authentication
        +
MFA Verification
        ↓
Successful AWS Login
```

## Learning Outcomes

Through this project, I learned:

* AWS IAM MFA
* Multi-Factor Authentication
* Virtual MFA Devices
* TOTP Authentication
* IAM User Security
* AWS Authentication
* Account Security Best Practices
* Additional Authentication Factors

## Screenshots

The `screenshots` folder contains evidence of:

1. IAM Users page
2. IAM user Security credentials
3. MFA configuration
4. Virtual MFA device setup
5. MFA device successfully assigned
6. MFA authentication during login

> **Security Note:** Do not upload QR codes, MFA secret keys, backup codes, passwords, or other sensitive authentication information to GitHub.

## Project Result

Successfully configured **Multi-Factor Authentication (MFA)** for an AWS IAM user and verified that MFA is required during authentication.

## Conclusion

This project demonstrated how MFA can strengthen AWS IAM security by requiring an additional verification factor during login.

Implementing MFA reduces the risk of unauthorized access and is an important part of a secure AWS identity and access management strategy.

### Key Concept

> **Password + MFA → Stronger AWS Account Security**
