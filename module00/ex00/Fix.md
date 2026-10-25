# XSS Mitigation Strategies

1. **Server-Side Sanitization:** Never trust client-side controls (like `maxlength`). Validate, filter, and strip executable characters from all inputs strictly on the backend server.
2. **Output Encoding:** Convert special characters into their secure HTML entities (e.g., `<` to `&lt;`, `>` to `&gt;`) before reflecting user data, ensuring the browser treats it strictly as text, not code.
3. **Content Security Policy (CSP):** Implement strict CSP HTTP headers to restrict the sources from which scripts can be loaded and block unauthorized inline scripts.
