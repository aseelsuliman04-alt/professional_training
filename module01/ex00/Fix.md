# SSTI Mitigation Strategies
1. **Never Concatenate Input into Templates:** Avoid dynamically generating template strings with user input. Instead, use safe variable passing. The engine will naturally treat the variable as data, not executable code.
2. **Use Logic-less Templates:** Whenever possible, switch to logic-less template engines (like Mustache) that strictly separate code from data and do not allow complex object traversal or code execution.
3. **Implement Strict Sandboxing:** If dynamic template generation is absolutely necessary, run the template environment in a highly restricted sandbox. Disable access to dangerous modules (like `os` or `subprocess`).
