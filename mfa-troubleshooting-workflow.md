# Microsoft 365 MFA Troubleshooting Workflow

## Overview

This guide documents a step-by-step workflow for troubleshooting Multi-Factor Authentication issues in Microsoft 365 and Entra ID environments.

MFA issues are common in IT support and MSP environments. Users may be unable to approve sign-ins, receive repeated prompts, lose access to their Authenticator app, replace their phone, or experience issues after security defaults or Conditional Access changes.

## Common Symptoms

Users may report:

* Unable to approve MFA prompt
* New phone does not have Microsoft Authenticator configured
* Repeated MFA prompts in Outlook or Teams
* MFA prompt does not appear
* User is stuck in an authentication loop
* User receives “More information required” message
* User cannot access email, Teams, or Microsoft 365 portal
* User changed phone number or lost access to old device

## Initial Questions to Ask

Before making changes, gather basic information:

* What application is affected? Outlook, Teams, browser, VPN, or all Microsoft 365 apps?
* Is the issue happening on one device or multiple devices?
* Did the user recently get a new phone?
* Is the user able to sign in through a private browser window?
* Is the issue affecting only one user or multiple users?
* Does the user still have access to their MFA method?
* Has the user recently changed password or had a license change?

## Troubleshooting Steps

### 1. Verify the User Account Status

In the Microsoft 365 Admin Center or Entra ID Admin Center:

* Confirm the user account exists.
* Confirm the account is not blocked.
* Confirm the account is enabled.
* Verify the user has the correct license assigned.
* Confirm there are no obvious account restrictions.

### 2. Review Authentication Methods

In Entra ID:

1. Open the user account.
2. Go to authentication methods.
3. Review registered methods such as:

   * Microsoft Authenticator
   * Phone number
   * Email
   * Temporary Access Pass
   * FIDO2 security key, if applicable

Check whether the user has an outdated phone number, old Authenticator registration, or missing authentication method.

### 3. Test Browser Sign-In

Ask the user to test sign-in using:

* A private or incognito browser window
* A different browser
* The Microsoft 365 portal
* A known working network, if possible

This helps determine whether the issue is browser cache related, device specific, or account related.

### 4. Review Sign-In Logs

In Entra ID, review the user's sign-in logs.

Check for:

* Failed sign-in attempts
* Conditional Access failures
* MFA requirement failures
* Blocked sign-ins
* Legacy authentication attempts
* Location-based restrictions
* Device compliance issues

Sign-in logs are useful because they show whether the issue is caused by MFA, Conditional Access, password failure, or another access control.

### 5. Reset MFA Registration if Needed

If the user has a new phone, lost access to Authenticator, or cannot approve prompts, an administrator may need to require re-registration of MFA.

Common admin actions may include:

* Require re-register multifactor authentication
* Delete outdated authentication methods
* Add or verify a phone number
* Issue a Temporary Access Pass, if supported by policy
* Confirm security information registration status

After reset, have the user sign in again and complete MFA setup.

### 6. Check Conditional Access Impact

If Conditional Access is used, review whether a policy is affecting the user.

Check:

* User assignment
* Group assignment
* Cloud app assignment
* Location condition
* Device compliance requirement
* MFA requirement
* Sign-in risk or user risk policies
* Exclusions for break-glass or service accounts

Conditional Access issues can appear as MFA problems when the actual cause is device compliance, location blocking, or policy misconfiguration.

### 7. Clear Cached Credentials

If MFA works in the browser but not in Outlook or Teams, clear cached credentials.

Possible steps:

* Sign out of Office apps.
* Close Outlook and Teams.
* Remove cached work or school account from Windows settings.
* Clear entries from Credential Manager if needed.
* Restart the device.
* Sign back into Microsoft 365 apps.

### 8. Confirm Resolution

After remediation:

* Have the user sign into Microsoft 365 portal.
* Confirm Outlook opens successfully.
* Confirm Teams signs in successfully.
* Confirm MFA prompt works.
* Verify the user's authentication methods are current.
* Document the resolution.

## Escalation Criteria

Escalate the issue if:

* Multiple users are affected.
* Conditional Access policies are failing unexpectedly.
* Sign-in logs show suspicious activity.
* The user reports MFA prompts they did not initiate.
* There are signs of possible account compromise.
* Admin changes do not resolve the issue.
* Licensing or tenant-level security settings appear misconfigured.

## Security Considerations

MFA troubleshooting should be handled carefully because it directly affects account security.

Important considerations:

* Verify the user’s identity before resetting MFA.
* Do not disable MFA unless specifically approved.
* Avoid bypassing security controls without authorization.
* Review sign-in logs for suspicious activity.
* Revoke sessions if account compromise is suspected.
* Document all changes clearly.

## Example Ticket Note

Issue:
User was unable to complete MFA after receiving a new phone.

Troubleshooting:
Verified account was active and licensed. Reviewed authentication methods in Entra ID and confirmed the user’s previous Authenticator registration was still associated with the account. Required MFA re-registration and had the user sign in through a private browser window to complete setup.

Resolution:
User successfully registered Microsoft Authenticator on the new phone and confirmed access to Microsoft 365, Outlook, and Teams.

## Skills Demonstrated

* Microsoft 365 administration
* Entra ID troubleshooting
* MFA support
* Identity and access management
* Sign-in log review
* Conditional Access awareness
* User support documentation
