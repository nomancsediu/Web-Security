# Path Traversal

Path traversal (also known as directory traversal) allows attackers to access files and directories outside the intended directory by using sequences like `../` in file paths.

## Attack Example

```
https://example.com/download?file=../../../etc/passwd
```

## Prevention

- Validate and sanitize all file path inputs
- Use chroot jails or restrict base directories
- Normalize paths before validation
- Never pass user input directly to filesystem operations
- Use allowlists of permitted files or directories
