# Outlook Sign-In Issues Troubleshooting

## Overview

This guide documents a troubleshooting workflow for Outlook sign-in issues in Microsoft 365 environments. Outlook problems are common in help desk and MSP support roles and may be caused by account issues, MFA prompts, cached credentials, profile corruption, licensing problems, network connectivity, or Microsoft service issues.

## Common Symptoms

Users may report:

- Outlook keeps asking for a password
- Outlook is stuck on “Trying to connect”
- Outlook says “Need password”
- Outlook cannot open the mailbox
- User can sign into webmail but not Outlook desktop
- Outlook repeatedly prompts for MFA
- Outlook profile will not load
- Outlook shows disconnected or offline
- User receives an authentication loop
- Outlook works on one device but not another

## Initial Questions to Ask

Before making changes, gather basic information:

- Is the issue affecting Outlook desktop, Outlook on the web, or both?
- Can the user sign into Microsoft 365 through a browser?
- Is the issue happening on one device or multiple devices?
- Did the user recently change their password?
- Did the user recently get a new phone or reset MFA?
- Is Teams or OneDrive also affected?
- Is the mailbox licensed correctly?
- Are other users affected?

## Troubleshooting Steps

### 1. Confirm Microsoft 365 Web Access

Ask the user to sign into:

- Microsoft 365 portal
- Outlook on the web
- Teams web

If web access works but Outlook desktop does not, the issue is likely local to the device, Outlook profile, cached credentials, or Office authentication.

If web access fails too, review the user account, password, MFA, license, or Conditional Access.

### 2. Verify User Account and License

In the Microsoft 365 Admin Center:

- Confirm the account is active.
- Confirm the account is not blocked.
- Confirm the user has the correct Microsoft 365 license.
- Confirm Exchange Online is enabled under the license apps.
- Confirm the mailbox exists and is not soft-deleted.

### 3. Review MFA and Authentication Methods

If Outlook is repeatedly prompting for credentials or MFA:

- Review the user’s authentication methods in Entra ID.
- Confirm the user can complete MFA.
- Check if the user recently changed phones.
- Test sign-in using a private browser window.
- Review sign-in logs for MFA failures.

### 4. Check Outlook Connection Status

On the affected computer:

- Confirm the device has internet access.
- Confirm the user is not working offline.
- Restart Outlook.
- Restart the computer.
- Test another Microsoft 365 app such as Teams or OneDrive.

### 5. Clear Cached Credentials

If the issue appears to be local to the device, clear cached credentials.

Possible steps:

1. Close Outlook and all Office applications.
2. Open Credential Manager.
3. Remove old Microsoft, Office, Outlook, or ADAL-related credentials.
4. Open Windows Settings.
5. Go to Accounts.
6. Review Work or school account connections.
7. Disconnect and reconnect the work account if appropriate.
8. Restart the computer.
9. Open Outlook and sign in again.

### 6. Create a New Outlook Profile

If Outlook still fails:

1. Open Control Panel.
2. Search for Mail.
3. Select Show Profiles.
4. Create a new Outlook profile.
5. Add the user’s Microsoft 365 mailbox.
6. Set the new profile as default.
7. Open Outlook and test.

A new profile can resolve corruption or stale configuration issues.

### 7. Check Autodiscover and DNS

If multiple users or a domain-wide issue is occurring, verify Autodiscover.

Check:

- Microsoft 365 service health
- Exchange Online status
- Autodiscover DNS records
- Recent DNS changes
- Mailbox migration status
- Tenant-wide authentication issues

### 8. Review Sign-In Logs

In Entra ID, review sign-in logs for the affected user.

Look for:

- Failed authentication
- Conditional Access failures
- MFA failures
- Device compliance failures
- Legacy authentication attempts
- Blocked sign-ins
- Unusual locations

### 9. Repair Office

If Outlook continues failing locally:

- Run Quick Repair.
- If needed, run Online Repair.
- Confirm Office is updated.
- Restart the computer after repair.

## Escalation Criteria

Escalate if:

- Multiple users are affected.
- Microsoft 365 service health shows an active issue.
- Sign-in logs show suspicious activity.
- Conditional Access is blocking access unexpectedly.
- Mailbox appears missing or corrupted.
- Outlook repair and profile recreation do not resolve the issue.
- DNS or Autodiscover appears misconfigured.

## Security Considerations

Outlook sign-in issues can sometimes indicate account compromise or suspicious login activity.

Review for:

- MFA prompts the user did not initiate
- Sign-ins from unusual locations
- Impossible travel alerts
- Multiple failed login attempts
- Suspicious inbox rules
- Unauthorized forwarding rules
- New device registrations

If compromise is suspected:

- Reset the password.
- Revoke active sessions.
- Review MFA methods.
- Review mailbox rules.
- Escalate to security.

## Example Ticket Note

Issue:
User reported Outlook desktop repeatedly prompting for credentials and not loading mailbox.

Troubleshooting:
Confirmed user could access Outlook on the web. Verified account was active and properly licensed. Reviewed authentication methods and sign-in logs with no suspicious failures. Cleared cached Office credentials from Credential Manager and restarted the device. Outlook continued prompting, so a new Outlook profile was created.

Resolution:
Outlook successfully connected after creating a new profile. User confirmed mailbox access was restored.

## Skills Demonstrated

- Outlook troubleshooting
- Microsoft 365 administration
- Exchange Online support
- Credential cache troubleshooting
- MFA awareness
- Sign-in log review
- User support documentation
