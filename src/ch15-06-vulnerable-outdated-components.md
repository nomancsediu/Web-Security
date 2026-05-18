# Vulnerable and Outdated Components

Using components with known vulnerabilities is a significant risk, especially given the complexity of modern software supply chains.

## Risk Factors

- You don't know all the components you use
- The software is vulnerable or outdated
- You don't scan for vulnerabilities regularly
- You don't fix underlying platforms in a timely fashion

## Prevention

- Maintain a software bill of materials (SBOM)
- Remove unused dependencies
- Continuously monitor for vulnerabilities (CVE databases)
- Use automated tools (Dependabot, Snyk, npm audit)
- Only obtain components from official sources
