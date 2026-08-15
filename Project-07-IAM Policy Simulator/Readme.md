# Project 7: IAM Policy Simulator

## Objective

Use the **AWS IAM Policy Simulator** to test and verify IAM permissions before applying them in a real AWS environment.

## Project Overview

In this project, I used the **IAM Policy Simulator** to check whether an IAM user or role has permission to perform specific AWS actions.

The simulator helps identify whether an action is:

* **Allowed**
* **Denied**

This is useful for troubleshooting IAM permissions and validating policies.

## AWS Services Used

* AWS IAM
* IAM Policy Simulator
* Amazon EC2

## Architecture

```text
                 IAM User / Role
                       │
                       ▼
                IAM Policy
                       │
                       ▼
             IAM Policy Simulator
                       │
              ┌────────┴────────┐
              ▼                 ▼
           Allowed             Denied
              │                 │
              ▼                 ▼
       Action Permitted    Action Blocked
```

## Project Scenario

For this project, I tested EC2 permissions using the IAM Policy Simulator.

The goal was to verify that the IAM policy allows the required EC2 actions while preventing unauthorized actions.

### Example Permissions Tested

```text
ec2:DescribeInstances
ec2:StartInstances
ec2:StopInstances
ec2:TerminateInstances
```

## Implementation Steps

### Step 1: Open IAM Policy Simulator

1. Logged in to the AWS Management Console.
2. Opened **IAM**.
3. Accessed the **Policy Simulator**.

### Step 2: Select IAM User or Role

Selected the IAM identity whose permissions needed to be tested.

The simulator evaluated the permissions associated with the selected identity.

### Step 3: Select AWS Service

Selected:

```text
Amazon EC2
```

### Step 4: Select Actions

Selected EC2 actions to test.

For example:

```text
DescribeInstances
StartInstances
StopInstances
TerminateInstances
```

### Step 5: Run the Simulation

Ran the policy simulation.

The simulator evaluated the selected actions against the IAM policies attached to the selected identity.

### Step 6: Review Results

The simulator displayed the permission result for each action.

Example:

```text
Action                  Result
--------------------------------
DescribeInstances       Allowed
StartInstances          Allowed
StopInstances           Allowed
TerminateInstances      Denied
```

The exact results depend on the IAM policy configured for the project.

## Verification

The IAM Policy Simulator was used to verify whether specific EC2 actions were permitted or denied.

### Expected Result

```text
Required EC2 Actions
        ↓
IAM Policy Simulator
        ↓
Permission Evaluation
        ↓
Allowed / Denied
```

This confirms whether the IAM policy is working as intended.

## Why Use IAM Policy Simulator?

The Policy Simulator is useful because it allows administrators and developers to:

* Test IAM permissions.
* Troubleshoot access denied errors.
* Verify policies before deployment.
* Identify unnecessary permissions.
* Understand how multiple policies affect access.
* Follow the principle of least privilege.

## Security Best Practices

* Grant only the permissions required.
* Test policies before applying them to production users.
* Avoid unnecessary `*` permissions.
* Regularly review IAM policies.
* Use the principle of least privilege.
* Do not grant `AdministratorAccess` when limited permissions are sufficient.
* Remove unused permissions.

## Learning Outcomes

Through this project, I learned:

* IAM Policy Simulator
* IAM Policies
* IAM Permissions
* Allow and Deny decisions
* EC2 permissions
* Permission troubleshooting
* Policy testing
* Principle of Least Privilege
* AWS IAM Security

## Screenshots

The `screenshots` folder contains evidence of:

1. IAM Policy Simulator
2. Selected IAM user or role
3. Selected EC2 service
4. EC2 actions being tested
5. Allowed permission result
6. Denied permission result

> **Security Note:** Do not upload passwords, AWS Access Keys, Secret Access Keys, MFA secrets, or other sensitive credentials to GitHub.

## Project Result

Successfully used the **AWS IAM Policy Simulator** to test and verify IAM permissions for EC2 actions.

The simulator clearly showed which actions were **Allowed** and which were **Denied** according to the configured IAM policies.

## Conclusion

This project provided hands-on experience with IAM permission testing and troubleshooting.

The IAM Policy Simulator is a useful tool for understanding how IAM policies affect access to AWS resources. It helps verify permissions before deployment and supports the implementation of secure, least-privilege access.

### Key Concept

> **Create Policy → Simulate Permissions → Verify Allowed/Denied → Apply Securely**
