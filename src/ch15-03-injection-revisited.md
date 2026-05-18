# Injection (Revisited)

Injection remains a top risk, encompassing SQL injection, NoSQL injection, OS command injection, and LDAP injection.

## Why Injection Persists

Despite being well-understood, injection vulnerabilities continue to appear because:

- Developers still concatenate user input into queries
- Legacy code contains vulnerable patterns
- ORMs can be misused
- New technologies introduce new injection surfaces

## Comprehensive Prevention

- Use parameterized queries consistently
- Validate all input
- Escape output based on context
- Use ORMs correctly
- Implement WAF as additional protection
