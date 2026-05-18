# X-Frame-Options and CORP

The X-Frame-Options header prevents clickjacking by controlling whether a page can be embedded in an iframe.

## X-Frame-Options Values

- `DENY` - Page cannot be framed at all
- `SAMEORIGIN` - Page can only be framed by same-origin pages

## Cross-Origin Resource Policy (CORP)

CORP controls who can embed a resource cross-origin:

- `same-origin` - Only same-origin can embed
- `same-site` - Only same-site can embed
- `cross-origin` - Any origin can embed

These headers work together with COEP and COOP to provide comprehensive cross-origin isolation.
