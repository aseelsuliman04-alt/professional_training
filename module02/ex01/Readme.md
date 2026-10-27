# Insecure Deserialization leading to Remote Code Execution (RCE)

## What is OWASP?
The Open Worldwide Application Security Project (OWASP) is a nonprofit foundation dedicated to improving software security. In the OWASP Top 10, Insecure Deserialization is classified under **A08: Software and Data Integrity Failures**.

## Vulnerability Explanation
* **Serialization:** The process of converting an object in memory into a byte stream or string (often encoded in Base64) to store it or transmit it across a network.
* **Deserialization:** The reverse process of reconstructing that byte stream back into a live object in memory.
**Insecure Deserialization** occurs when an application deserializes untrusted, user-supplied data without verification. In Python (Flask) applications using the `pickle` module, the deserialization process automatically invokes the `__reduce__()` magic method to reconstruct the object. An attacker can craft a malicious object where `__reduce__()` instructs the server to execute arbitrary operating system commands (`os.system`), leading directly to **Remote Code Execution (RCE)**.
