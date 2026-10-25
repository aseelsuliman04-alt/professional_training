# CSRF Mitigation Strategies

1. **Anti-CSRF Tokens:** Implement unpredictable, session-unique tokens (Synchronizer Token Pattern). The server generates a unique token and includes it in hidden form fields. The server then validates this token on every state-changing request (POST, PUT, DELETE).
2. **SameSite Cookie Attribute:** Set the `SameSite` attribute for session cookies to `Strict` or `Lax`. This prevents the browser from sending cookies along with cross-site requests, effectively neutralizing most CSRF attacks.
3. **Require Re-authentication:** For highly sensitive actions (like money transfers or password changes), force the user to re-enter their password or use multi-factor authentication (MFA) to confirm the action.
