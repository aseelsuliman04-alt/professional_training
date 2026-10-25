# Exploitation Payloads and Scenarios
## Payload Used
The following payload targets a Python/Flask application using the Jinja2 template engine. It traverses the object hierarchy to import the `os` module and execute a system command:
```python
{{request.application.__globals__.__builtins__.__import__('os').popen('cat /etc/passwd').read()}} ```
## Exploitation Scenarios
1. **Data Exfiltration:** An attacker can read sensitive system files (like `/etc/passwd`, environment variables containing API keys, or database credentials) by executing commands such as `cat` or `env`.
2. **Server Takeover (RCE):** The attacker can spawn a reverse shell, install malware, or completely hijack the underlying operating system infrastructure by running malicious shell commands through the template engine.
