# XSS (Cross-Site Scripting)

## What is OWASP?
The Open Worldwide Application Security Project (OWASP) is a nonprofit focused on software security, best known for publishing the "OWASP Top 10" list of critical web vulnerabilities.

## Vulnerability Explanation
XSS occurs when an application reflects unsanitized user input directly into a webpage. This allows attackers to inject malicious scripts that the victim's browser executes, trusting the legitimate server.

## Exploitation Scenarios
1. **Session Hijacking:** Injecting a script to read and steal `document.cookie`, allowing the attacker to hijack the victim's active session.
2. **Phishing:** Injecting a fake HTML login form over the real site to capture and steal user credentials.
