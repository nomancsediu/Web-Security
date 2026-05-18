# Injection Attacks

Injection attacks occur when untrusted data is sent to an interpreter as part of a command or query. The attacker's hostile data tricks the interpreter into executing unintended commands or accessing unauthorized data. Injection flaws are among the most common and dangerous web vulnerabilities, consistently ranking at the top of the OWASP Top 10.

This chapter covers the various types of injection attacks that target web applications. You will learn how each type of injection works, how to identify vulnerable code, and how to defend against these attacks using parameterized queries, input validation, and other proven techniques.

Injection attacks are particularly dangerous because they can lead to complete system compromise. A successful SQL injection, for example, can allow an attacker to read, modify, or delete the entire database. Command injection can give attackers shell access to the server. Understanding these attacks is essential for any web developer or security professional.
