# Shared Mailbox Troubleshooting

## Overview

This guide documents a troubleshooting workflow for shared mailbox issues in Microsoft 365 and Exchange Online environments.

Shared mailbox problems are common in IT support and MSP environments. Users may be unable to access a shared mailbox, send as the mailbox, send on behalf of the mailbox, or see the mailbox automatically appear in Outlook.

## Common Symptoms

Users may report:

- Shared mailbox does not appear in Outlook
- User cannot open the shared mailbox
- User cannot send as the shared mailbox
- User cannot send on behalf of the shared mailbox
- Sent items are not saving where expected
- Shared mailbox works in webmail but not Outlook desktop
- User receives permission denied errors
- Mailbox appears for one user but not another
- Outlook is slow after adding a shared mailbox

## Important Permission Types

### Full Access

Allows a user to open and view the shared mailbox.

### Send As

Allows a user to send email as the shared mailbox. The recipient sees the message as coming from the shared mailbox.

### Send on Behalf

Allows a user to send on behalf of the shared mailbox. The recipient can see that the message was sent by the user on behalf of the mailbox.

## Troubleshooting Steps

### 1. Confirm the Shared Mailbox Exists

In Microsoft 365 Admin Center or Exchange Admin Center:

- Confirm the shared mailbox exists.
- Confirm the mailbox is active.
- Confirm the email address is correct.
- Confirm it is actually configured as a shared mailbox.

### 2. Verify User Permissions

Review permissions assigned to the user.

Check:

- Full Access permission
- Send As permission
- Send on Behalf permission
- Group-based access, if used
- Whether the correct user account was assigned

If a user needs to open and send as the shared mailbox, they may need both Full Access and Send As.

### 3. Allow Time for Permissions to Apply

Mailbox permission changes may take time to apply.

After adding permissions:

- Wait for propagation.
- Have the user restart Outlook.
- Have the user sign out and back in.
- Test in Outlook on the web.

### 4. Test in Outlook on the Web

Ask the user to test using Outlook on the web.

Steps:

1. Open Outlook on the web.
2. Select the user profile icon or mailbox option.
3. Choose Open another mailbox.
4. Enter the shared mailbox address.
5. Confirm whether the mailbox opens.

If it works in webmail but not Outlook desktop, the issue is likely local Outlook cache, profile, or auto-mapping.

### 5. Check Auto-Mapping

Auto-mapping controls whether the shared mailbox automatically appears in Outlook.

If the mailbox does not appear automatically:

- Confirm Full Access permission exists.
- Remove and re-add permissions if needed.
- Manually add the shared mailbox in Outlook.
- Create a new Outlook profile if necessary.

### 6. Manually Add the Shared Mailbox

In Outlook desktop:

1. Go to Account Settings.
2. Select the user’s account.
3. Choose More Settings.
4. Go to Advanced.
5. Add the shared mailbox.
6. Restart Outlook.

### 7. Check Send As or Send on Behalf

If the user can open the mailbox but cannot send:

- Confirm whether the user needs Send As or Send on Behalf.
- Verify the correct permission was assigned.
- Test from Outlook on the web.
- Confirm the From field is enabled in Outlook.
- Remove and re-add the shared mailbox address in the From field.

### 8. Review Outlook Profile or Cache Issues

If the issue only occurs in Outlook desktop:

- Restart Outlook.
- Update Office.
- Clear cached credentials.
- Disable and re-enable cached mode if appropriate.
- Create a new Outlook profile.
- Test Outlook on another device.

### 9. Review Licensing Requirements

Shared mailboxes usually do not require a license if they are under Microsoft’s size and feature limits.

A license may be needed if:

- The mailbox exceeds size limits.
- Litigation hold is required.
- Microsoft Defender or advanced features are needed.
- Archive mailbox features are required.

## Security Considerations

Shared mailboxes should be reviewed regularly because they can provide access to sensitive business communication.

Important practices:

- Assign access only to approved users.
- Use groups where appropriate.
- Review permissions periodically.
- Remove access when users change roles or leave.
- Avoid granting unnecessary Send As permissions.
- Document who requested and approved access.

## Example Ticket Note

Issue:
User reported they could not access the accounting shared mailbox in Outlook.

Troubleshooting:
Verified the shared mailbox existed in Exchange Admin Center. Confirmed the user did not have Full Access permission. Added Full Access and Send As permissions based on approved request. Had the user test in Outlook on the web successfully. User restarted Outlook desktop and confirmed the mailbox appeared.

Resolution:
Shared mailbox access restored. User confirmed they could open the mailbox and send as the shared mailbox.

## Escalation Criteria

Escalate if:

- Permissions appear correct but access still fails after propagation.
- Multiple users are affected.
- Mailbox appears corrupted or missing.
- Outlook profile recreation does not resolve the issue.
- There are concerns about unauthorized access.
- The mailbox contains sensitive or regulated data requiring review.

## Skills Demonstrated

- Exchange Online administration
- Shared mailbox permissions
- Outlook troubleshooting
- Microsoft 365 support
- Access control review
- User support documentation
