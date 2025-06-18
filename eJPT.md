
---

# Information Gathering

## Passive

|File|Description|
|:---:|:---:|
|/robots.txt|Folders that should not be crawled by indexers|
|/sitemap.xml|For search engines to index a site in an organized way|

1. **Host**, IPv4/IPv6/mail connected to domain :

```bash
host <domain>
```

2. **whatweb**, Identifies  web technologies used on site:
```bash
whatweb <domain>
```

3. **whatweb**, Download an entire website to the local computer:
```bash
whatweb <domain> -o <path>
```

4. **DNSRecon**, Checks and enumerats all DNS records:
```bash
dnsrecon -d <domain>
```

```bash
dnsrecon -d <domain> -n <dns nameserver> --lifetime <time>
```

5. **wafw00f**, -l to list firewalls, -a test all poissible WAF instances
```bash
wafw00f <domain>
```

6. **Sublist3r**, Numeration of of subdomains

|Flag|Description|
|:---:|:---:|
|-d|Domain name to enumerate subdomains of|
|-b|Enable the subbrute bruteforce module|
|-p|Scan the found subdomains against specific tcp ports|
|-v|verbose mode and display results in realtime|
|-t|Number of threads to use for subbrute bruteforce|
|-e|Specify a comma-separated list of search engines|
|-o|Save the results to text file|
|-h|show the help message and exit|

Excluding -e will perform a search on all engines

```bash
sublist3r -d <domain> -e <engine> 
```

7. **theHarvester** - Recognizance gathers emails, subdomains and IP-addresses using OSINT. To list help and sources use -h
   to list sources and help:
```bash
theHarvester -d <company/domain> -b <source>
```

8. Google Dorks
   
|Flag|Description|
|:---:|:---:|
|site:domain.com|List results for domain, using *. infront of domain will list subdomains|
|inurl:input|Searches for a specific text within a URL|
|intitle:input|Filters on on specified word in the page title|
|filetype:filetype|Searches for a specific filetype|
|cache:domain|Displayes a cached domain|
|intitle:"index of"|Common vulnerability, developers might expose directories, old builds and more|

**Sites** - [Whois](https://who.is/), [Netctaft](https://sitereport.netcraft.com/), [DNSDumpster](https://www.dnsdumpster.com/), [Have I Been Pwned](https://www.haveibeenpwned.com), [Google Dorks](https://www.exploit-db.com/google-hacking-database), [Wayback Machine](https://web.archive.org/)

## Active
|Record|Description|
|:---:|:---:|
|A|Resolves a hostname or domain to an IPv4 address|
|AAAA|Resolves a hostname or domain to an IPv6 address|
|NS|Reference to the domains nameserver|
|MX|Resolves a domain to a mail server|
|CNAME|Used for domain aliases|
|TXT|Text record|
|HINFO|Host information|
|SOA|Domain authority|
|SRV|Service records|
|PTR|Resolves an IP address to a hostname|

9. **dnsenum**, enumerates DNS records
```bash
dnsenum <domain>
```

10. **dig**, zone transfer using dig 
```bash
dig AXFR @<name server> <domain.domain> 
```

11. **fierce**, DNS reconnaissance tool used to locate non-contiguous IP spaces 
```bash
fierce -dns <domain>
```

11. **nmap**, Network exploration and security auditing

|Commands|Description|
|:---:|:---:|
|-sn|Ping sweep - will not peform port scans only print available hosts|
|-Pn|Disables host discovery (ping), assumes the host is up|
|-p-|Scans the entire TCP port range|
|-p <port>|Scan a specific port|
|-p<range>-<range>|Port scans a range|
|-F|Fast mode, scans the 100 commonly used TCP ports|
|-sU|UDP port scan|
|-v|verbosity|
|-sV|Service version|
|-O|Detect operating system|
|-sC|Script Scan|
|-T<number>|Speed of a scan, the higher number the more agressive|
|-oN <output.txt>|Saves the output as a txt|
|-oX <output.xml>|Saves the output as a xml|

Scan a range
```bash
sudo nmap -sn <ip>/24
```
---

# Assessment Methodologies: Footprinting & Scanning 

##
