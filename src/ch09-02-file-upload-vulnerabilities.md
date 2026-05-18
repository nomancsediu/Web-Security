# File Upload Vulnerabilities

File upload functionality is common in web applications but introduces significant security risks if not implemented correctly.

## Attack Vectors

- **Remote code execution** - Uploading executable files (PHP, JSP, etc.)
- **Path traversal** - Overwriting critical files via filename manipulation
- **XSS via file content** - Uploading HTML/SVG files with embedded scripts
- **Denial of service** - Uploading extremely large files
- **MIME type confusion** - Bypassing type checks via content-type spoofing

## Prevention

- Validate file type by content (magic bytes), not just extension
- Store uploaded files outside the web root
- Use randomly generated filenames
- Set proper file permissions
- Implement file size limits
- Scan uploads for malware
