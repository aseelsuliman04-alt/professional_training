# Server-Side Template Injection (SSTI)

## What is OWASP?
The Open Worldwide Application Security Project (OWASP) is a nonprofit foundation that works to improve the security of software.

## Vulnerability Explanation
Server-Side Template Injection (SSTI) is a vulnerability that occurs when user input is unsafely embedded directly into a server-side template before it is rendered by the template engine. Instead of treating the input as plain text, the engine parses and executes it as code. In environments like Python (Jinja2), this allows an attacker to escape the sandbox and execute arbitrary system commands (Remote Code Execution - RCE) on the server.
