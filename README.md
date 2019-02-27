# BugBounty
Cheat Sheets, Methodologies etc.


## Subdomain Scraping

### Subfinder

[https://github.com/ice3man543/subfinder](https://github.com/ice3man543/subfinder)

`subfinder -d domain.name -o /path/to/output`


## DNS Resolving

### MassDNS

[https://github.com/blechschmidt/massdns](https://github.com/blechschmidt/massdns)

`massdns -r ./massdns/lists/resolvers.txt -t A -o S /path/to/subfinderoutput > /path/to/output`

Get uniq IPs:

`cat /path/to/massdnsoutput | grep -E "A " | sed 's/.*A //' | sort | uniq > UniqIPs.txt`

## Port Scanning

### Masscan

[https://github.com/robertdavidgraham/masscan](https://github.com/robertdavidgraham/masscan)

`masscan -iL UniqIPs.txt -p<portrange> --rate <somerate> > /path/to/output`
