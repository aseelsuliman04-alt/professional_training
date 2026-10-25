# Server-Side Request Forgery (SSRF) & Local File Inclusion (LFI)
## What is OWASP?
The Open Worldwide Application Security Project (OWASP) is a nonprofit foundation that works to improve the security of software.
## Vulnerability Explanation
* **Server-Side Request Forgery (SSRF):** A web security vulnerability that allows an attacker to induce the server-side application to make requests to an unintended location.
* **Local File Inclusion (LFI):** A vulnerability that allows an attacker to include or read local files stored on the server through the web browser.

In this challenge, the application fetches content from a user-supplied URL without validating the protocol or destination, allowing an attacker to combine SSRF and LFI using the `file://` URI scheme to read sensitive local system files.
