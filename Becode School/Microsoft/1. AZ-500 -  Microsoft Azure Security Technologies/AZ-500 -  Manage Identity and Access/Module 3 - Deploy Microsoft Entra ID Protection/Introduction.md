# Explore Microsoft Entra ID Protection

Identity Protection is a tool that allows organizations to accomplish three key tasks:

- Automate the detection and remediation of identity-based risks.
- Investigate risks using data in the portal.
- Export risk detection data to third-party utilities for further analysis.

Identity Protection uses the learnings Microsoft has acquired from their position in organizations with Microsoft Entra ID, the consumer space with Microsoft Accounts, and in gaming with Xbox to protect your users. Microsoft analyzes 6.5 trillion signals per day to identify and protect customers from threats.

Risk detections in Microsoft Entra ID Protection include any identified suspicious actions related to user accounts in the directory. The signals generated that are fed to Identity Protection, can be further fed into tools like Conditional Access to make access decisions, or fed back to a security information and event management (SIEM) tool for further investigation based on your organization's enforced policies.

Identity Protection provides organizations access to powerful resources so they can quickly respond to suspicious activities.

## Identity Protection policies

Microsoft Entra ID Protection includes three default policies that administrators can choose to enable. These policies include limited customization but are applicable to most organizations. All the policies allow for excluding users such as your emergency access or break-glass administrator accounts.

![Screenshot of the three policies described in the content.](https://learn.microsoft.com/en-us/training/wwl-azure/azure-ad-identity-protection/media/az500-identity-protection-2455a26b.png)

## Azure Multi-Factor Authentication registration policy

Identity Protection can help organizations roll out Azure Multi-Factor Authentication using a Conditional Access policy requiring registration at sign-in. Enabling this policy is a great way to ensure new users in your organization have registered for MFA on their first day. Multi-factor authentication is one of the self-remediation methods for risk events within Identity Protection. Self-remediation allows your users to act on their own to reduce helpdesk call volume.

## Sign-in risk policy

Identity Protection analyzes signals from each sign-in, both real-time and offline, and calculates a risk score based on the probability that the sign-in wasn't performed by the user. Administrators can decide based on this risk score signal to enforce organizational requirements. Administrators can choose to block access, allow access, or allow access but require multi-factor authentication.

If risk is detected, users can perform multi-factor authentication to self-remediate and close the risky sign-in event to prevent unnecessary noise for administrators.

## Custom Conditional Access policy

Administrators can also choose to create a custom Conditional Access policy, including sign-in risk as an assignment condition.