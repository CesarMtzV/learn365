# Domain Enumeration
___
Index | Topic
--- | ---
**1** | Tools
**2** | Examples

## Tools

- assetfinder
- amass
- ffuf

## Example

- Subdomain enumeration: `assefinder --subs-only somedomain.com`
- Subdomain enumeration: `amass enum -d somedomain.com -brute`
  - Providing a custom config file `amass enum -d somedomain.com -brute -config ~/.config/amass`
- Subdomain enumeration: `ffuf -w namelist.txt -u http://FUZZ.somedomain.com -m 200,302,301,403,401,500 2>/dev/null`
- Directory enumeration: `ffuf -w common.txt -u http://www.somedomain.com/FUZZ 2>/dev/null`

