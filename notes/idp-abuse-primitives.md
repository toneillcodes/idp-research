# IdP Abuse Primitives
## Introduction
An **abuse primitive** (often used interchangeably with attack primitive) refers to a basic, **foundational attack technique** that leverages an existing, **legitimate feature, configuration setting, or design mechanism** of a system in an **unintended, malicious way**.  

It's a discrete atomic action that exploits how a system is designed to work, rather than a bug or vulnerability in its code.  

Attackers chain these primitives together to form an attack path to achieve a larger goal, such as privilege escalation or gaining persistence.  

In this portion of my research, I am exploring primitives within modern IdP platforms.

## Taxonomy
### Challenges
Existing frameworks for threat categorization are not designed to capture the necessary level of detail required for formal protocol analysis of IdP platforms. Frameworks like MITRE ATT&CK focus on the adversary’s strategic behavior, detailing Tactics, Techniques, and Procedures (TTPs). For instance, ATT&CK may catalog the high-level technique of "Persistence via Cloud Application Integration", which is useful for defense analysts identifying gaps. However, these frameworks often fail to articulate the atomic mechanism used.
