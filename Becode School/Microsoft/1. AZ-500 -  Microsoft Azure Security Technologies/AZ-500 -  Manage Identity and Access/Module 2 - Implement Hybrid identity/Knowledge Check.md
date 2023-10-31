Let's go through the questions one by one:

1. The IT helpdesk wants to reduce password reset support tickets. You suggest having users sign in to both on-premises and cloud-based applications using the same password. Your organization does not plan on using Microsoft Entra ID Protection, so which feature would be easiest to implement given the requirements?

   - Federation
   - Pass-through authentication
   - Password hash synchronization

   **Answer:** Password hash synchronization `This option just shares the password hash between two federated systems.`

2. Which tool can you use to synchronize Microsoft Entra passwords with on-premises Active Directory?

   - Microsoft Entra Connect
   - Active Directory Federation Services
   - Password writeback

   **Answer:** Microsoft Entra Connect `Microsoft Entra Connect. Microsoft Entra Connect Sync is a main component of Microsoft Entra Connect. It takes care of all the operations that are related to synchronize identity data between your on-premises environment and Microsoft Entra ID.`

3. Microsoft Entra ID supports which of the following security protocols?

   - Kerberos
   - OAuth
   - OpenID Connect

   **Answer:** OAuth `OAuth is used for authorization.`

4. Which of the following is an authentication option that integrates with Microsoft Entra ID, requiring you to use several differing methods, like your phone, to confirm your identity?

   - FIDO2 security keys
   - Microsoft Authenticator app
   - Microsoft Entra multifactor authentication

   **Answer:** Microsoft Entra multifactor authentication `Microsoft Entra multifactor authentication (MFA) is a great way to secure your organization, but users often get frustrated with the extra security layer on top of having to remember their passwords. Passwordless authentication methods are more convenient because the password is removed and replaced with something you have, plus something you are or something you know. The other choices are passwordless authentication options that integrate with Microsoft Entra ID. Microsoft Entra Domain Services) enables the use of ciphers such as NTLM v1 and TLS v1.`

Please note that technology and services may evolve over time, so it's important to refer to the latest documentation and updates from Microsoft for the most accurate and up-to-date information.