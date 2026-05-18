# NoSQL Injection

As NoSQL databases like MongoDB, CouchDB, and Redis have gained popularity, a new class of injection attacks has emerged. NoSQL injection exploits the differences in query syntax and evaluation mechanisms specific to NoSQL databases.

## MongoDB Injection

MongoDB queries use JavaScript-like object syntax. An attacker can exploit this by injecting query operators. For example, a login query:

```javascript
db.users.find({ username: username, password: password })
```

If the attacker sends `{ "$ne": "" }` as the password, the query matches any user where the password is not empty, bypassing authentication.

## Prevention

- Validate and sanitize input types (ensure strings, not objects)
- Use MongoDB's query language carefully
- Apply the principle of least privilege to database accounts
- Use middleware to filter input before it reaches the database
