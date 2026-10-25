# Exploitation Payloads and Scenarios

## Payloads Used
By abusing the URL fetching functionality, we use the `file://` protocol wrapper instead of `http://` to force the server to read its own local filesystem:

```text
file:///etc/passwd
```
## Exploitation Scenarios:
1. Sensitive Local File Disclosure (LFI via SSRF): An attacker can use the file:// schema to read sensitive configuration files, source code, SSH keys, or system files like /etc/passwd directly from the server.
2. Internal Network Scanning and Cloud Metadata Access (SSRF): An attacker can force the server to send requests to internal-only services (e.g., http://127.0.0.1:8080/admin) or cloud provider metadata endpoints (such as http://169.254.169.254/latest/meta-data/) to steal credentials and take over the infrastructure.

