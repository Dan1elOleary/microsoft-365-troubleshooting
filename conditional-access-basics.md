# Conditional Access Basics

## Overview

This guide provides a basic overview of Microsoft Entra ID Conditional Access and common troubleshooting considerations.

Conditional Access is used to control access to cloud applications based on user, device, location, risk, application, and session conditions. It helps organizations enforce security controls such as MFA, compliant device requirements, and location-based restrictions.

## What Conditional Access Does

Conditional Access answers a basic question:

If a user tries to access a resource, under certain conditions, what controls should be required?

Example:

If a user signs into Microsoft 365 from outside the trusted office location, require MFA.

## Common Conditional Access Conditions

Conditional Access policies may evaluate:

- User or group membership
- Cloud application being accessed
- Device platform
- Device compliance status
- Location
- Sign-in risk
- User risk
- Client application
- Browser or mobile app session
- Authentication strength

## Common Access Controls

Policies may require:

- Multi-Factor Authentication
- Compliant device
- Hybrid Azure AD joined device
- Approved client app
- App protection policy
- Password change
- Terms of use acceptance
- Block access

## Common Symptoms

Users may report:

- Unable to sign into Microsoft 365
- MFA prompts happen more often than expected
- Access works in the office but not remotely
- Access works on one device but not another
- Outlook works but Teams does not
- Browser access works but desktop app fails
- User is blocked due to location or device compliance
- User receives a message that access has been blocked

## Troubleshooting Steps

### 1. Confirm the Affected User and Application

Gather:

- User account
- Application affected
- Device used
- Location or network
- Time of the failed sign-in
- Screenshot of the error
- Whether the issue affects one user or multiple users

### 2. Review Sign-In Logs

In Entra ID:

1. Open the user account.
2. Go to sign-in logs.
3. Find the failed sign-in event.
4. Review the Conditional Access tab.

Look for:

- Policy applied
- Policy result
- Grant control required
- Failure reason
- Device compliance status
- Location information
- Client app used

### 3. Identify the Blocking Policy

In the sign-in log details, check which Conditional Access policy caused the failure.

Common causes include:

- MFA required but not completed
- Device is not compliant
- User is outside an approved location
- Legacy authentication is blocked
- User is not using an approved app
- Risk-based policy blocked the sign-in
- User is not excluded from a policy that should not apply

### 4. Check User and Group Assignment

Review whether the policy applies to:

- All users
- Specific users
- Specific groups
- Guest users
- Directory roles

Also check exclusions.

Be careful with exclusions because excluding users from security policies can weaken security.

### 5. Check Cloud App Assignment

Confirm the policy applies to the intended application.

Examples:

- Office 365
- Exchange Online
- SharePoint Online
- Microsoft Teams
- All cloud apps
- Specific third-party applications

### 6. Check Device Compliance

If the policy requires a compliant device, confirm:

- Device is enrolled.
- Device is marked compliant.
- Required security settings are present.
- The user is signing in from the correct device.
- The device object exists in Entra ID or Intune.

### 7. Check Location Conditions

If the policy uses location:

- Confirm the user’s public IP address.
- Confirm trusted locations are configured correctly.
- Confirm VPN or remote network behavior.
- Check whether the sign-in is coming from an unexpected country or region.

### 8. Check Legacy Authentication

Many organizations block legacy authentication because it does not support modern security controls like MFA.

If an app uses legacy authentication, the user may be blocked.

Examples of legacy protocols may include:

- IMAP
- POP
- SMTP AUTH
- Older Office clients
- Basic authentication

### 9. Use Report-Only Mode When Testing

When creating or modifying policies, report-only mode can help test the impact before enforcement.

Report-only mode allows administrators to see what would happen without actively blocking users.

## Best Practices

- Use least privilege.
- Require MFA for risky or external access.
- Block legacy authentication.
- Use named locations carefully.
- Exclude emergency break-glass accounts from strict policies.
- Test policies before broad enforcement.
- Avoid applying new policies to all users without validation.
- Review sign-in logs before changing policy settings.
- Document policy purpose and business justification.

## Security Considerations

Conditional Access is a powerful security control. Misconfigured policies can either block legitimate users or allow risky access.

Important considerations:

- Do not disable policies without approval.
- Avoid broad exclusions.
- Protect admin accounts with stronger controls.
- Monitor sign-in logs regularly.
- Review policy changes after implementation.
- Maintain emergency access accounts.

## Example Ticket Note

Issue:
User was unable to access Microsoft Teams while working remotely.

Troubleshooting:
Reviewed Entra ID sign-in logs and found a Conditional Access failure. The applied policy required a compliant device for Teams access. The user was signing in from a personal device that was not enrolled or marked compliant. Confirmed the policy was working as intended.

Resolution:
Advised user to access Teams from a managed compliant device or follow the approved device enrollment process.

## Escalation Criteria

Escalate if:

- Multiple users are unexpectedly blocked.
- A policy change caused widespread access issues.
- Admin accounts are blocked.
- Sign-in logs show suspicious or risky behavior.
- Device compliance data appears inaccurate.
- A business-critical app is inaccessible.
- A policy requires review by security leadership.

## Skills Demonstrated

- Entra ID administration
- Conditional Access troubleshooting
- Sign-in log review
- MFA and device compliance awareness
- Identity and access management
- Security policy analysis
- Technical documentation
