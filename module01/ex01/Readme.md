# XML External Entity (XXE) Injection
## What is OWASP?
The Open Worldwide Application Security Project (OWASP) is a nonprofit foundation that works to improve the security of software.

## Vulnerability Explanation
XML External Entity (XXE) injection is a web security vulnerability that allows an attacker to interfere with an application's processing of XML data. It occurs when a weakly configured XML parser processes XML input containing a reference to an external entity. This allows an attacker to view files on the application server filesystem, and to interact with any backend or external systems that the application itself can access.
