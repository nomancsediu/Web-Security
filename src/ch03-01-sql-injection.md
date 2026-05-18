# SQL Injection

SQL Injection (SQLi) is one of the most well-known and impactful web vulnerabilities. It occurs when user input is incorporated into SQL queries without proper sanitization or parameterization, allowing attackers to manipulate the query's logic.

## How SQL Injection Works

Consider a login query like:

```sql
SELECT * FROM users WHERE username = '{username}' AND password = '{password}'
```

If an attacker enters `' OR '1'='1` as the username, the query becomes:

```sql
SELECT * FROM users WHERE username = '' OR '1'='1' AND password = ''
```

Since `'1'='1'` is always true, the query returns all users, bypassing authentication.

## Types of SQL Injection

### In-Band SQL Injection
The attacker uses the same communication channel to launch the attack and gather results. This includes error-based and union-based SQLi.

### Blind SQL Injection
The attacker asks the database true/false questions and observes the application's response to infer data. This includes boolean-based and time-based blind SQLi.

### Out-of-Band SQL Injection
The attacker uses different channels to launch the attack and gather results, such as making the database send data to an external server.

## Prevention

- **Use parameterized queries (prepared statements)** - This is the most effective defense
- **Use ORMs** - Most ORMs automatically parameterize queries
- **Input validation** - Validate and sanitize all user input
- **Least privilege** - Database accounts should have minimal necessary permissions
- **Web Application Firewall** - Can detect and block SQL injection attempts
