# Command Injection

Command injection occurs when an application passes user input to a system shell command. If the input is not properly sanitized, an attacker can inject additional commands that are executed with the privileges of the application.

## Example

Consider a web application that pings a user-provided IP address:

```python
import os
ip = request.getParameter('ip')
os.system('ping -c 4 ' + ip)
```

An attacker could provide input like `8.8.8.8; cat /etc/passwd`, which would execute both the ping command and the `cat /etc/passwd` command.

## Prevention

- **Avoid shell commands** - Use language-native libraries instead of shell commands
- **Input validation** - Use whitelist validation (e.g., only allow IP address format)
- **Parameterized execution** - Use execvp or similar functions that don't invoke a shell
- **Least privilege** - Run the application with minimal necessary permissions
