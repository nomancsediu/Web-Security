# Software and Data Integrity Failures

This category covers code and infrastructure that does not protect against integrity violations, including using software from untrusted sources and insecure CI/CD pipelines.

## Examples

- Insecure deserialization
- Unsigned or unverified code updates
- CI/CD pipeline compromises
- Auto-update functionality without integrity verification

## Prevention

- Use digital signatures to verify software integrity
- Verify library dependencies
- Use SRI for CDN resources
- Secure CI/CD pipelines
- Implement code review processes
