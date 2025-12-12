# IdP Primitives List
## Overview
The goal of this page is to develop and collect a list of potential abuse primitives.  
The list was initially compiled by reviewing the functionality provided by the WSO2 Identity Server platform.  

| Category | Technique | Sub-Technique | Description | Detection/Notes |
| :--- | :--- | :--- | :--- | :--- |
| **AI** | **Malicious MCP Server** | Add malicious MCP server | Attacker registers a rogue MCP server in the identity system to gain trust and access tokens. | |
| AI | Malicious MCP Server | Scope Over-Provisioning on Malicious MCP Server | Assigns excessive or privileged scopes to the malicious MCP server, enabling access to sensitive tools or data. | |
| AI | Malicious MCP Server | Response Manipulation by MCP Server | MCP server injects malicious responses or instructions into AI workflows (e.g., prompt injection via MCP tool responses). | |
| AI | Malicious MCP Server | Exfiltration via MCP Server | MCP server collects sensitive data from AI tools and sends it to attacker-controlled endpoints. | |
| AI | Malicious MCP Server | MitM MCP Server | Attacker sets up a proxy MCP server that forwards requests to legitimate servers while intercepting or altering data. | |
| AI | Malicious MCP Server | Token Replay or Forgery via MCP Server | MCP server misuses issued tokens to impersonate clients or escalate privileges. | |
| **Authentication** | **Downgrading Authentication Controls** | Disable SAML assertion signing for federated IdPS | Adversaries disable SAML assertion signing in federated identity providers to allow token forgery and bypass integrity checks. | Monitor IdP configuration changes; alert when signature validation is disabled. |
| Authentication | Downgrading Authentication Controls | Disable SAML assertion signing per SP | Adversaries disable SAML assertion signing for service providers to allow token forgery and bypass integrity checks. | |
| Authentication | **Malicious authentication flow** | Malicious adaptive authentication policy | Adversaries inject malicious adaptive authentication code into the authentication process. | |
| Authentication | **MFA enrollment tampering** | Change MFA settings | Ability to change MFA or register a new device with only a type 1 authenticator | I don't think this notifies users of changes |
| Authentication | Malicious authentication flow | Abuse of magic link flow | Email users a magic link to log in passwordless; Mail attribute or mailbox rule manipulation to avoid detection | |
| Authentication | Malicious authentication flow | Modify Flows | Self-Registration, Password Recovery, Invited User Registration | |
| Authentication | Downgrading Authentication Controls | Disable or downgrade brute force protection | Changing login attempt threshold settings | |
| Authentication | Downgrading Authentication Controls | Disable captcha | Disabling functionality to weaken authentication controls | |
| Authentication | Downgrading Authentication Controls | Increase session timeout interval | Increases window of abuse for tokens/cookies | |
| Authentication | **Session manipulation** | Extend session API | `https://<IS_HOST>:<IS_PORT>/t/<TENANT_DOMAIN>/identity/extend-session` | |
| **Exfiltration** | **Logging user activity** | Remote logging to attacker controlled resource | | |
| Exfiltration | **Bulk data extraction** | Bulk user export for data exfil | `https://github.com/wso2/samples-is/tree/master/bulk-user-export-tool` | |
| Exfiltration | Logging user activity | Malicious webhook to send monitor events to an attacker controlled resource | | |
| **Management** | **Create standard user** | Create user | Primary identity vault or internal IdP store; Should this be a Persistence category? | |
| Management | **Create privileged user** | Create user | Primary identity vault or internal IdP store; Should this be a Persistence category? | |
| Management | **Create service account** | Create user | Primary identity vault or internal IdP store; Should this be a Persistence category? | |
| Management | **Create group** | Create new group | | |
| Management | **Alter group permissions** | Change group permissions | | |
| Management | **Malicious management workflow** | Malicious workflow to manage users or roles | | |
| **Notification** | **Disable notifications** | Disable Email notifications for Impersonation functionality | | |
| Notification | Disable notifications | Disabling webhooks to blind monitoring soutions | | |
| **Persistence** | **Account recovery** | Linked Account abuse | myaccount link accountsLink/associate your other accounts, and access them seamlessly without re-login | |
| Persistence | Account recovery | Account Recovery Backup Codes | TBD | TBD |
| Persistence | **Claim manipulation - expand on this** | TBD | TBD | TBD |
| Persistence | **Abuse of Actions - expand on this** | `https://is.docs.wso2.com/en/latest/complete-guides/actions/pre-issue-access-token-action-use-case/` | TBD | TBD |
| Persistence | **Keystore management API abuse** | | | |
