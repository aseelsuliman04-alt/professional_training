# Exploitation Payloads and Scenarios

## Payload Used
The following XML payload exploits the XXE vulnerability by defining an external entity (`xxe`) that references the local `/etc/passwd` file. When the XML is parsed, the entity is evaluated, and the file's contents are returned in the response.

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<!DOCTYPE data [
  <!ELEMENT data ANY >
  <!ENTITY xxe SYSTEM "file:///etc/passwd" >
]>
<data>&xxe;</data> 
```

# Exploitation Scenarios:
1. Local File Disclosure: An attacker can read sensitive files stored on the server, such as configuration files containing database passwords, system user data (like /etc/passwd), or source code.
2. Server-Side Request Forgery (SSRF): An attacker can force the server to make HTTP requests to internal systems that are not publicly accessible, potentially exposing internal admin panels or cloud infrastructure metadata.
