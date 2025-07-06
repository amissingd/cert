## Site

|File|Description|
|:---:|:---:|
|/robots.txt|Folders that should not be crawled by indexers|
|/sitemap.xml|For search engines to index a site in an organized way|

## Google Dorks
   
|Flag|Description|
|:-------:|:---:|
|site:domain.com|List results for domain, using *. infront of domain will list subdomains|
|inurl:input|Searches for a specific text within a URL|
|intitle:input|Filters on on specified word in the page title|
|filetype:filetype|Searches for a specific filetype|
|cache:domain|Displayes a cached domain|
|intitle:"index of"|Common vulnerability, developers might expose directories, old builds and more|

**Sites** - [Whois](https://who.is/), [Netctaft](https://sitereport.netcraft.com/), [DNSDumpster](https://www.dnsdumpster.com/), [Have I Been Pwned](https://www.haveibeenpwned.com), [Google Dorks](https://www.exploit-db.com/google-hacking-database), [Wayback Machine](https://web.archive.org/)


1. **whatweb**, Technologies used on site, -o <path> to download the site
```bash
whatweb <domain>
```

2. **DNSRecon**, Checks and enumerats all DNS records
```bash
dnsrecon -d <domain> -n <dns nameserver> --lifetime <time>
```

3. **wafw00f**, -l to list firewalls, -a test all poissible WAF instances
```bash
wafw00f <domain>
```

4. **Sublist3r**, Numeration of of subdomains, -e to specify engine
```bash
sublist3r -d <domain> -e <engine> 
```

5. **theHarvester** - Recognizance gather emails, subdomains and IP-addresses for OSINT
```bash
theHarvester -d <company/domain> -b <source>
```

6. **dnsenum**, enumerates DNS records
```bash
dnsenum <domain>
```

7. **dig**, zone transfer using dig 
```bash
dig AXFR @<name server> <domain.domain> 
```

8. **fierce**, DNS reconnaissance tool used to locate non-contiguous IP spaces 
```bash
fierce -dns <domain>
```

## Ping sweeps

9. **fping**
```bash
fping -a -g <ip/<subnet> 2>/dev/null
```

## Nmap Scan
10. **Nmap** 

*Scan range*
```bash
sudo nmap -sn <ip>/24
```

*Quick Scanning*
```bash
nmap -sC -sV <IP>
```

*Full Scanning*
```bash 
nmap -sC -sV -T4 <IP>
```

*Combined service version, script skanning, operation system & traceroute*
```bash 
nmap -A -Pn -p- <IP>
```

*UDP Scanning*
```bash
nmap -sU -sV <IP>
```
*Useful flags: -O for OS detection and -Pn if targeting firewall/microsoft, -oN or -oX <path> to export results as txt or xml*

10. **nmap**, within MSF
```bash 
db_nmap <options>
```
### Nmap Scripts

Nmap script directory /usr/share/nmap/script/

11. **Nmap scripts**
```bash
nmap --script-help=<script>
```

## SMB

12. **smbclient** -L lists shares, -u for specific user
```bash
smbclient -L \\\\<ip>\\ -U <username>
```

13. **enum4linux**, -a does simple enumeration
```bash
enum4linux -a -S <wordlist path>
```

## MSF

14. **MSF wordlists**
```bash
 /usr/share/metasploit-framework/data/wordlists/
```

|Commands|Description|
|:---:|:---:|
|workspace -a name|Create a workspace|
|db_status|Status for MSF|
|db_import path|Import data externally|
|search x / use x|Search for module/exploit> / use a specific module / showing options for a module|
|info / show options|Shows information about selected module / shows options for selected module|
|setg variable|set a global variable|
|loot / cred|shows information gained after SMB enumeration|

15. Search for specific auxiliary/exploit,
```bash
search type:auxiliary/exploit name:<name>
```

16. **Searchsploit for MSF**
```bash
searchsploit  “<exploit>” | grep -e “Metasploit”
```

17. **davtest**
```bash
davtest -auth<user:password> -url<url>
```

18. **hydra**
```bash
hydra -L <user wordlist> -P <password wordlist>
```
