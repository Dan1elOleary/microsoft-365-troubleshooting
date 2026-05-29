# Microsoft 365 New User Onboarding Checklist

## Overview

This checklist documents a structured workflow for onboarding a new Microsoft 365 user. It is designed for IT support, MSP, and help desk environments where consistency, accuracy, and documentation are important.

A proper onboarding process helps ensure that the user has the correct account, license, mailbox, group memberships, security settings, and access needed before their start date.

## Pre-Onboarding Information Needed

Before creating the account, gather:

- Full legal name
- Preferred display name
- Job title
- Department
- Manager
- Start date
- Work location
- Required email address
- Required phone number, if applicable
- Required Microsoft 365 license
- Required security groups
- Required distribution lists
- Required shared mailbox access
- Required Teams or SharePoint access
- Required applications
- Hardware or workstation assignment

## Account Creation Checklist

### 1. Create the User Account

In Microsoft 365 Admin Center or Entra ID:

- Create the user account.
- Confirm the username and email address.
- Set the display name.
- Add job title and department.
- Add manager information if available.
- Set the correct usage location.
- Assign a temporary password if required.

### 2. Assign Licensing

Assign the correct Microsoft 365 license.

Verify that required services are enabled, such as:

- Exchange Online
- Microsoft Teams
- OneDrive
- SharePoint
- Office desktop apps
- Defender or security add-ons, if applicable

### 3. Configure Mailbox

After the mailbox provisions:

- Confirm mailbox creation.
- Confirm primary email address.
- Add aliases if needed.
- Configure mailbox permissions if required.
- Add shared mailbox access if required.
- Add distribution list memberships if required.

### 4. Configure Groups and Access

Add the user to required:

- Security groups
- Microsoft 365 groups
- Distribution lists
- Teams
- SharePoint sites
- Department groups
- Application access groups

Use group-based access where possible to simplify management.

### 5. Configure MFA and Security Information

Prepare the user for MFA registration.

Steps may include:

- Confirm MFA policy applies.
- Confirm security defaults or Conditional Access requirements.
- Have the user register Microsoft Authenticator.
- Confirm backup authentication methods if allowed.
- Verify phone number or alternate email if required.
- Provide instructions for first sign-in.

### 6. Review Conditional Access Impact

If Conditional Access is used, verify whether the user is affected by policies requiring:

- MFA
- Compliant device
- Approved app
- Trusted location
- Password change
- Sign-in risk review

Confirm that the user will not be blocked unexpectedly on their first day.

### 7. Prepare Device Access

If the user receives a company device:

- Confirm device assignment.
- Confirm Windows updates are installed.
- Confirm required applications are installed.
- Confirm antivirus or EDR is active.
- Confirm device is enrolled in management, if applicable.
- Confirm local admin settings follow company policy.
- Confirm BitLocker status, if applicable.

### 8. Application Access

Verify access to required business applications.

Examples:

- Microsoft Teams
- Outlook
- OneDrive
- SharePoint
- Line-of-business apps
- VPN
- Password manager
- Ticketing system
- RMM tools, if applicable
- Role-specific software

### 9. Send Welcome or Setup Instructions

Provide user-friendly instructions for:

- First sign-in
- Temporary password change
- MFA setup
- Outlook access
- Teams access
- Password reset process
- Support contact information

## Security Considerations

New user onboarding should follow least privilege.

Important practices:

- Only assign access required for the user’s role.
- Avoid direct permissions when group-based access is available.
- Verify manager or department approval for sensitive access.
- Require MFA.
- Avoid sharing passwords through insecure channels.
- Review privileged access separately.
- Document all assigned access.

## Post-Onboarding Validation

After setup:

- Confirm the user can sign into Microsoft 365.
- Confirm Outlook mailbox access.
- Confirm Teams access.
- Confirm OneDrive access.
- Confirm required application access.
- Confirm MFA registration.
- Confirm the user has the correct groups.
- Document completion in the ticket.

## Example Ticket Note

Request:
New user onboarding for employee starting on Monday.

Actions Taken:
Created Microsoft 365 user account, assigned appropriate license, configured mailbox, added required security groups and distribution lists, confirmed Teams and SharePoint access, and prepared MFA registration instructions. Verified account status and documented assigned access.

Status:
User account is ready for first sign-in. MFA registration will be completed by the user during initial login.

## Offboarding Reminder

Every onboarding process should have a matching offboarding process.

Common offboarding actions include:

- Block sign-in
- Reset password
- Revoke sessions
- Remove licenses
- Convert mailbox to shared mailbox if needed
- Remove group memberships
- Remove application access
- Transfer OneDrive ownership if required
- Disable or remove device access

## Skills Demonstrated

- Microsoft 365 administration
- Entra ID user management
- Licensing review
- Mailbox setup
- Group-based access management
- MFA preparation
- Endpoint onboarding awareness
- Technical documentation
