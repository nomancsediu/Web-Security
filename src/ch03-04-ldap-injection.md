# LDAP Injection

LDAP injection attacks exploit applications that construct LDAP queries from user input. Similar to SQL injection, LDAP injection allows attackers to modify the logic of LDAP queries to bypass authentication, access unauthorized data, or modify LDAP directory entries.

## Example

A login query might look like: `(& (uid={username})(userPassword={password}))`. An attacker entering `*)(|(&` as the username could bypass authentication.

## Prevention

- Use parameterized LDAP queries
- Encode and escape LDAP special characters
- Validate input against expected patterns
- Apply least privilege to LDAP service accounts
