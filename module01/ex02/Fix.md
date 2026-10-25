# SSRF & LFI Mitigation Strategies
1. **Restrict Allowed URL Schemas (Protocols):** Configure the URL fetching mechanism to only allow safe protocols such as `http://` and `https://`, and explicitly block dangerous schemas like `file://`, `gopher://`, `dict://`, and `ftp://`.
2. **Implement a Strict Allowlist (Whitelist):** Validate user-supplied URLs against a strict allowlist of trusted domains and IP addresses before the server makes any outbound request.
3. **Block Private/Internal IP Ranges:** Ensure the server resolves the target domain name and blocks requests directed at loopback addresses (`127.0.0.1`, `localhost`), internal private networks, and cloud metadata IPs (`169.254.169.254`).
