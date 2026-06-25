# Recon

## 1. **Basic Reconnaissance (Passive OSINT)**

> No interaction with the target, avoids detection.
> 
- **WHOIS & Domain Intelligence**
    - `whois` `Whoxy` 
    - `DomainBigData` `OCCRP Aleph`
    - `Kaferjaeger.gay`
    - Identify registrars, name servers, emails, organization.
    - 
- **DNS Enumeration**
    - `dig`, `nslookup`, `dnsrecon`, `fierce`
    - Collect subdomains, mail servers, TXT records (SPF/DMARC).
- **Search Engines**
    - Google Dorking: `site:example.com filetype:pdf`
    - Shodan Dorking `shodan stats --facets domain:1000 'What do you want to search here'`
    - Censyus Dorking
    - LinkedIn for employees → spear-phishing usernames.
- **Wayback Machine / Archive.org**
    - Look for old endpoints, forgotten panels, staging environments.
    - https://www.virustotal.com/vtapi/v2/domain/report?apikey={api}&domain={domain.com}
      
    - https://otx.alienvault.com/api/v1/indicators/domain/domain.com/url_list?limit=100&page=2
    	- A script for this is found in the `python/tools` repo name `alienvalut_grep.py` 
       ```
       # grep domains
       curl -s "https://otx.alienvault.com/api/v1/indicators/domain/domain.com/url_list?limit=2000&page=4" | grep -oE "[a-zA-Z0-9.-]+\.suddomain\.domain\.com" | sort -u
       ```
       ```
       # verbose (params and all)
       curl -s "https://otx.alienvault.com/api/v1/indicators/domain/main.domain/url_list?limit=2000&page=3" \
		| jq -r '.url_list[] | select(.url | contains("urs.testing.main.domain")) | .url'
       ```
    
	- https://web.archive.org/cdx/search/cdx?url=*.domain.com&fl=original&collapse=urlkey
    
	- urlscan.io

- **Image OSINT**
    
    Google image search : `yandex` `tineye`
    
- **Public Repositories**
    - GitHub/GitLab/Bitbucket leaks: API keys, credentials.
    - Tools: `truffleHog`, `git-secrets`.
        
        Technology Fingerprinting : `wappulyzer`
        Version detection of services
        Source Code
        
- **Media Recon**
    - Stack technology leaks: "We’re hiring a DevOps engineer with AWS, Terraform, Kubernetes experience" = tech stack exposed. ( job postings )
    - Social Media Recon
    - Location recon
    - Satellite images
    - Employee Recon
    - Instagram / Facebook /Twitter /  and all….
        
         `sherlcok`
        
        `whatsapp.checkleaked.cc`
        
- **Hunting**
    - Fingerprint exposed services globally.
    - Data breaches: `weleakinfo` `pimeyes` `dehashed` `leakcheck` `haveibeenpwned`
    - Emails  credential stuffing targets.
        
        [`Hunter.io`](http://hunter.io/) [`Phonebook.cz`](http://phonebook.cz/) `VoilaNorbert` `rocketreach`
        
        breaches such as : [`intelx.i](http://intelx.io)o` `haveibeenpwnd` `leakradar.io`
        
        Verifying email: `Email Hippo` `Email checker`
        
________________________________________________________________________________________________________________________________________________________________________________________________________
## 2. **Intermediate Reconnaissance (Active, but low-noise)**

> Starts interacting with the target but still stealthy.
> 
- **Subdomain Enumeration**
    - Tools: `subfinder`, `amass`, `assetfinder`, `crt.sh`
    - Bruteforce with wordlists (`dnscan`, `dnsx`)
- **Port Scanning**
    - `nmap -sV -sC -T4 target.com`
    - Service version detection & default scripts.
- **Virtual Host Discovery**
    - Tools: `ffuf -H "Host: FUZZ.example.com" -u http://IP`
    - directory / vhost discovery
- **Directory Bruteforcing**
    - Web path enumeration
    - Directory traversal tests
    - Tools: `gobuster`, `ffuf`, `dirsearch`
    - Wordlists: `SecLists` `wordlists.assetnote.io`
    - JS endpoint extraction and link crawling
    - Header-based scanning (`x-forwarded-for`, `x-origin`)
- **SSL/TLS Recon /  Censys lookup**
    - Check certs for SANs (Subject Alt Names).
    - Tools: `sslscan`, `testssl.sh`.
- **Cloud Asset Discovery**
    - AWS S3 Buckets: `aws s3 ls s3://bucket-name`
    - Tools: `cloud_enum`, `s3scanner`.
________________________________________________________________________________________________________________________________________________________________________________________________________
## 3. **Advanced Reconnaissance (Deep Attack Surface Mapping)**

> Involves more aggressive scanning, correlation, and automation.
> 
- **ASN  Records & IP Space Enumeration**
    - Find all IP ranges owned by org.
    - Tools: `amass intel -asn <ASN>`, `bgp.he.net`
    - JS file parsing for endpoints
    - Reverse DNS lookups
    - CORS misconfiguration checks via headers
    - Endpoint wordlist generation using
    - Sitemaps/robots.txt/humans.txt abuse
- **Correlation of Domains & Subs**
    - Tools: `Amass`, `Chaos`, `ProjectDiscovery suite`
    - Combine results, deduplicate.
- **Web Tech Fingerprinting**
    - `wappalyzer`, `httpx`, `whatweb`
    - Identify frameworks, CMS, plugins → known CVEs.
    - WAF and CDN detection
- **Content Discovery Beyond Wordlists**
    - Param guessing: `paramspider`, `arjun`
    - Identify hidden APIs.
    - Content discovery (JS, JSON, config leaks)
- **Git Dorking**
    - Advanced GitHub code search for company leaks.
- **Network-Level Recon**
    - SNMP enumeration (if open): `snmpwalk`
    - SMB shares: `smbclient -L //target`
- **Automated Attack Surface Mapping**
    - Vulnerability scanning with custom Nuclei templates / Nessus
    - Frameworks: `reconFTW`, `BugMap`, `OSINT Framework`, `Nuclei`
    - Daily cronjobs to catch new assets.
________________________________________________________________________________________________________________________________________________________________________________________________________
## 4. **Expert-Level Reconnaissance (Red Team / APT Style)**

> Rarely done by casual hunters, but gold for pentesting.
> 
- **Supply Chain Recon**
    - Third-party vendors → weak links.
    - Identify partner domains, shared infra.
- **Endpoint & API Recon**
    - Decompile mobile apps → API endpoints.
    - Tools: `MobSF`, `apktool`
    - Swagger docs leaks: `/swagger.json`
- **Employee Recon**
    - Password reuse attacks, password spraying.
    - Username harvesting → OWA, VPN, SSO portals.
- **Custom Wordlist Generation**
    - From company docs, GitHub, LinkedIn.
    - Tools: `cewl`, `theHarvester`.
- **Cloud & Container Recon**
    - Kubernetes dashboards, Jenkins, Docker APIs.
- **Advanced Correlation**
    - Use BloodHound-style mapping for external assets.
    - Pivot via DNS records, CDN leaks, forgotten IPs.
 ________________________________________________________________________________________________________________________________________________________________________________________________________



# To Use:
_____________

**ASN records // ip spaces :**

- bgp.he.net
- dnschecker.org
- tracxn.com
___________________
**asnmap**

	$ echo GOOGLE | ./asnmap -silent
	
	$ echo hackerone.com | ./asnmap -json -silent | jq
______________________________________________________________________________________________________________________________

**naabu**

	$ naabu -list ips.txt -p - -s -o open_ports.txt
	
	$ naabu -host hackerone.com

	$ echo AS14421 | naabu -p 80,443

	$ echo hackerone.com | naabu -silent | httpx -silent
___________________
**TLSX**

	$ echo 173.0.84.0/24 | tlsx 
	
	$ echo 173.0.84.0/24 | tlsx -san -cn -silent
______________________________________________________________________________________________________________________________

**subfinder** [ Passive subdomain enumeration using multiple sources. ]

*Go to chaos and register an account, get the api key and put in subfinder = 15% more increase enumeration*

	$ subfinder -d example.com -all -silent -o subs.txt 

	$ subfinder -d example.com -recursive -o deep_subs.txt

	$ subfinder -d example.com -silent | httpx -silent -o live.txt

	$ chaos -d domain.com | alterx enrich  | dnsx
___________________
**asset finder** [ Quick subdomain finder ]

	$ assetfinder --subs-only example.com > asset.txt 

	$ assetfinder -v example.com

	$ assetfinder -live example.com

	$ assetfinder --timeout 10 --rate-limit 100 example.com

**crt.sh**
	
	$ curl -s https://crt.sh\?q\=\domain.com\&output\=json | jq -r '.[].name.value' | grep -Po '(\w+\.\w+\.\w+)$' | sort -u 

_____________________________________________________________________________________________________________________________

**amass** [ Powerful subdomain enumeration (passive + active + brute force) ]


	$ amass enum -d example.com -o amass.txt 
______________________________________________________________________________________________________________________________

**feroxbuster** [ fast, recursive content discovery tool ]


	$ feroxbuster -u https://target.com
	
	$ feroxbuster -u https://target.com -x php,txt,html --depth 2 

	$ feroxbuster -u http://example.com -w /usr/share/seclists/Discovery/Web-Content/raft-large-words.txt -t 100 -r --auto-tune -o ferox_results.txt

	$ feroxbuster -u http://example.com -w adminlist.txt -H "Authorization: Bearer <token>" -r -o admin_panels.txt

	$ feroxbuster -u http://example.com --extract-links -r -o discovered_links.txt
______________________________________________________________________________________________________________________________

**BBOT** [  Powerful subdomain enumeration  ]

	- Full subdomain enumeration (passive + active):
	$ bbot -t example.com -p subdomain-enum
	
	- Passive sources only:
	$ bbot -t example.com -p subdomain-enum -rf passive
	
	- Subdomains + port scan + web screenshots:
	 $ bbot -t example.com -p subdomain-enum -m naabu gowitness
	
	- Subdomains + web spider for email harvesting:
	 $ bbot -t example.com -p subdomain-enum web-spider
	
	 - $ bbot -t example.com -p subdomain-enum --output-modules json
______________________________________________________________________________________________________________________________

**linkfinder** [ Extract endpoints from JS files]

	$ python3 linkfinder.py -i https://example.com/app.js -o cli 

	$ python linkfinder.py -i https://example.com -d
____________________________________________________________________________
[crawl a web for JS files...]

 - Store both (URLs + endpoints)

	echo "https://example.com" | waybackurls | grep ".js" | while read url; do
	    echo "[+] Processing $url" >> results.txt
	    python3 linkfinder.py -i $url -o cli >> results.txt
	done
______________________________________________________________________________________________________________________________

**waybackurls** [ Fetch archived URLs from Wayback Machine. ]
	
	$ echo "domain.com" | waybackurls | tee urls.txt
	
	$ subfinder -d example.com -all | waybackurls > wayback.txt

**GAU** [ fetches known URLs ]

	$ gau example.com

	$ gau --providers wayback example.com

	$ gau --subs example.com
		- grep -i "://api.example.com" all_urls.txt > api_only_urls.txt

	$ gau --blacklist png,jpg,gif,svg,woff,woff2,css example.com

	$ gau example.com --subs | grep -iE "\.(xls|xml|xlsx|json|pdf|sql|doc|docx|pptx|txt|zip|tar\.gz|tgz|bak|7z|rar|log|cache|secret|db|backup|yml|yaml|md|exe|dll|bin|ini|bat|sh|deb|rpm|iso|img|apk|msi|dmg|tmp|crt|pem|key|pub|asc|env|git|sqlite|pfx|config|swp)$"
______________________________________________________________________________________________________________________________

**arjun** [ Parameter discovery ]
 
	$ arjun -u https://target.com -o arjun.txt

	$ arjun --passive example.com -oJ passive_params.json   

**Katana** [ web crawling ]

	$ katana -u https://example.com

	$ katana -u https://example.com -ps

	$ katana -u https://example.com -ef png,jpg,jpeg,gif,css,woff,svg,pdf

	$ katana -u https://example.com -jc
	
______________________________________________________________________________________________________________________________

**paramspider** [ Crawl and extract GET parameters from URLs. ]

	$ paramspider -d domain.com
	
	$ paramspider -l domains.txt
___________________________________________________

**spiderfoot** [ OSINT automation (subdomains, leaks, IPs, etc.) ]

	$ spiderfoot -s "example.com" -o json > spiderfoot.json 

	$ spiderfoot -s example.com -t EMAIL_ADDRESS -o csv > discovered_emails.csv
	
	$ spiderfoot -s example.com -t ACCOUNT_EXTERNAL_OWNED_DOMAIN -o tab

	$ spiderfoot -q -s example.com -m s3bucket,google_maps,github,pastebin -o tab | sort -u
```
		for url in $(cat live_urls.txt); do spiderfoot -s "$url" -o json > "${url//\//_}.json"; done
```
______________________________________________________________________________________________________________________________


**Httpx** [check live hosts]

	$ httpx -l subs.txt -o live.txt 
	
	$ httpx -l subs.txt -silent -o live.txt
	
	$ echo "domain.com" | waybackurls | tee urls.txt | httpx -title -status-code -content-length  -tech-detect | tee results.txt

______________________________________________________________________________________________________________________________

**gf** [- A wrapper around grep that u quickly filter interesting findings from large lists of URLs ]

	$ cat urls.txt | gf xss
___________________________________________________
**XSS findings**

	$ gf xss urls_0.txt | tee xss_0.txt
	
	$ cat urls.txt | gf xss > xss_candidates.txt
___________________________________________________
**redirects**

			$ gf redirect urls_0.txt | tee redirect_0.txt
______________________________________________________________________________________________________________________________

**Gxss** [ Check reflected parameters for potential XSS. ]

	$ cat "domain.txt" | Gxss > reflected_urls.txt
	$ cat xss_candidates.txt | Gxss -p XSS > reflected.txt
___________________________________________________

**dalfox** [ Actively scan/exploit XSS vulnerabilities.]

	$ dalfox file reflected_urls.txt
	$ cat reflected.txt | dalfox pipe -o xss_results.txt
______________________________________________________________________________________________________________________________

**Xss Loader** [ encoding the xss ]

	$ python3 payloader.py
______________________________________________________________________________________________________________________________

**Xss Strike** 

	$ python3 xsstrike.py -u https://example.com/search?q=test
	
	$ python3 xsstrike.py -u https://example.com --crawl
	
	$ python3 xsstrike.py -u https://example.com/search?q=test --skip-waf
___________________________________________________________________________________________________________________________

**exifdata XSS**

	exiftool -ImageDescription='<img src=x onerror=alert(1)>' image.jpg
____________________________________________________________________________

```
		exiftool \
		  -ImageDescription='<img src=x onerror=alert(1)>' \
		  -Artist='<svg onload=alert(2)>' \
		  -UserComment='<details open ontoggle=alert(3)>' \
		  -XPComment='" onmouseover="alert(4)' \
		  -Copyright='<iframe srcdoc="<script>alert(5)</script>"></iframe>' \
		  image.jpg
```
______________________________________________________________________________________________________________________________

**Nuclei**

- Finds exposed sensitive files like .env, backups, configs, logs, and git data.
```	nuclei -l https://target.com -t exposures/
	nuclei -u https://target.com -t exposures/backups/
	nuclei -u https://target.com -t exposures/ -severity high,critical
	nuclei -u https://target.com -t exposures/apis/
	nuclei -u https://target.com -t exposures/configs/
	nuclei -u https://target.com -t exposures/debug/
	nuclei -u https://sub.target.com -t http/exposed-panels/
```

- Detects insecure server/app settings like debug mode, open admin panels, unsafe methods.
```
	nuclei -u https://target.com -t misconfiguration/
```
- Tests common admin panels for default or weak credentials.
```
  nuclei -u https://target.com -t misconfiguration/default-login/
```
- Checks for known vulnerabilities based on CVE signatures.
```
  nuclei -u https://target.com -t cves/
```
- Identifies dangling DNS records that may allow subdomain takeover.
```
	nuclei -u https://sub.target.com -t takeovers/
```
- Local file Inclusion
```
	nuclei -u https://sub.target.com -t http/vulnerabilities/generic/generic-lfi.yaml
```

- Open Redirect
```
	nuclei -u https://sub.target.com -t http/vulnerabilities/generic/open-redirect-generic.yaml
```

______________________________________________________________________________________________________________________________

**graphql-cop** [ Test common misconfigurations of graphql endpoints ]

	$ python3 graphql-cop.py -t https://mywebsite.com/graphql

__________________________________________________________________________________________________________________________

# rough 

	$ cat file1 file2 | sort -u > file3  [ sort out files ] 
	
	$ cat out.txt | uro | grep -EE '(\.env|\.git|\.config|\.phpinfo|web\.config|settings\.py|composer\.json)$' [ Filter the highest impact files ]
	
	$ uro -i output.txt | rg -i '\.(xls|xml|xlsx|json|pdf|sql|doc|docx|pptx|txt|zip|tar\.gz|tgz|bak|7z|rar|log|cache|secret|db|backup|yml|yaml|md|exe|dll|bin|ini|bat|sh|deb|rpm|iso|img|apk|msi|dmg|tmp|crt|pem|key|pub|asc)$' 

*Google dorks*

				site:.example.com intext:Login
								
				site:*<*.target.*  // site:*<-*.target.* // site:*>*.target.*  // site:*->*.target.*  // site:*<->*.target.*

				site:.example.com ext:pdf  //  site:.example.com filetype:php  // site:.example.com "invoice" "receipt" ext:pdf  // site:domain.com ext:log | ext:txt | ext:conf | ext:json | ext:yaml | ext:yml

				site:.example.com before:YYYY-MM-DD // site:.example.com before:2015-01-01 

				site:.example.com inurl:? || inurl:&  // 		## returns results to example.com containing parameters (?,&)

				site:*.domain.com inurl:"error" | inurl:"debug" | inurl:"test" | inurl:"config"  // site:domain.com inurl:email= | inurl:id= | inurl:query= | inurl:search=
				
				site:.example.com (intext:Login OR intext:Register or intext:Create Account)

				site:.example.com AND (intitle:Login OR intitle:Register or intitle:Create An Account)

				site:.example.com (inurl:/signin OR inurl:/login OR inurl:/register)

				site:*<*.target.com intext:"login" | intitle:"login" | inurl:"login" | intext:"username" | intitle:"username" | inurl:"username" | intext:"password" | intitle:"password" | inurl:"password"

				site:domain.com & inurl:redir | inurl:url | inurl:redirect | inurl:return | inurl:src=http | inurl:r=http | inurl:redirectUrl=http

				site:example.com (inurl:url= | inurl:return= | inurl:next= | inurl:redirect= | inurl:redir= | inurl:ret= | inurl:r2= | inurl:page= | inurl:dest= | inurl:target= | inurl:redirect_uri= | inurl:redirect_url= | inurl:checkout_url= | inurl:continue= | inurl:return_path= | inurl:returnTo= | inurl:out= | inurl:go= | inurl:login?to= | inurl:origin= | inurl:callback_url= | inurl:jump= | inurl:action_url= | inurl:forward= | inurl:src= | inurl:http= | inurl:urlTo= | inurl:re= | inurl:view= | inurl:checkout= | inurl:&)

				site:example.com (inurl:url=|inurl:return=|inurl:next=|inurl:redirect=|inurl:redir=|inurl:ret=|inurl:r2=|inurl:page=|inurl:dest=|inurl:target=|inurl:redirect_uri=|inurl:redirect_url=|inurl:checkout_url=|inurl:continue=|inurl:return_path=|inurl:returnTo=|inurl:out=|inurl:go=|inurl:login?to=|inurl:origin=|inurl:callback_url=|inurl:jump=|inurl:action_url=|inurl:forward=|inurl:src=|inurl:http=|inurl:urlTo=|inurl:re=|inurl:view=|inurl:checkout=|inurl:&)

				site:domain.com inurl:swagger | inurl:api-docs | inurl:v1 | inurl:v2 | inurl:v3 | inurl:graphql
________________________________________________________________________________________________
		$ shodan search ssl.cert.subject.CN:"target.com" --fields ip_str | anew shodan.txt
				cat shodan.txt | naabu -top-ports 1000 | anew shodan_ports.txt
_______________________________________________________
	- cat subdomains-top1million-50000.txt | ffuf -w -:FUZZ -u http://example.com/ -H 'Host: FUZZ.example.com' -ac
_______________________________________________________
	## messy file?
		- cat messy.txt | grep "testing.com" | awk '{print $2}' | sort -u
		- cat messy.md | grep "200" | awk '{print $1}' | grep -vE "\.js($|\?)"
		
	## Extract All Domains from a messy file
	    - grep -Eoi '([a-zA-Z0-9\-]+\.)+[a-zA-Z]{2,6}' your_messy_file.txt | sort -u domains.txt
	
	## Extract All IPv4 Addresses from a messy file
	    - grep -Eoi '([0-9]{1,3}\.){3}[0-9]{1,3}' your_messy_file.txt | sort -u ipFile.txt
_______________________________________________________
*If you have a file containing ip's and want to find out who it belongs to quick*
```
- cat ips.txt | xargs -I {} sh -c 'echo "=== {} ==="; host {}; echo "Q" | openssl s_client -connect {}:443 -tls1_3 2>/dev/null | grep "subject="'
		  or
- cat test.txt | xargs -P 20 -I {} sh -c 'echo "=== {} ==="; host {}; echo "Q" | openssl s_client -connect {}:443 -tls1_3 2>/dev/null | grep "subject="'

## tlsx
-  tlsx -l ipFile.txt -san -cn -silent

- tlsx -l ipFile.txt -p 443,8443,9443 -san -cn -c 5 -scan-mode openssl -json -o ipInfo.json
tlsx -l ipFile.txt -p 443,8443,9443 -san -cn -ve -silent -json -o ipInfo.json

   format the json data
jq -r '[.ip, .port, .subject_cn, (.subject_an | join(","))] | @tsv' ipInfo.json
```
__________________________________________________________________________________________________________________________________________________________________
*Scrape all ips and domains from a page*
```
## Copy the ip ##

copy([...new Set(document.body.innerText.match(/\b(?:[0-9]{1,3}\.){3}[0-9]{1,3}\b/g))].join('\n')); console.log("[+] Unique IPs copied to your clipboard!");

## if you want both ip and port ##

copy([...new Set(document.body.innerText.match(/\b(?:[0-9]{1,3}\.){3}[0-9]{1,3}\b:\d+/g))].join('\n')); console.log("[+] Target IP:Port combos copied!");

or

const m = document.body.innerText.match(/(?:[0-9]{1,3}\.){3}[0-9]{1,3}\s*:\s*\d+/g) || []; copy([...new Set(m.map(x => x.replace(/\s+/g, '')))].join('\n')); console.log("[+] Unique targets copied cleanly!");

or

{ const targets = document.body.innerText.match(/(?:[0-9]{1,3}\.){3}[0-9]{1,3}\s*:\s*\d+/g) || []; copy([...new Set(targets.map(x => x.replace(/\s+/g, '')))].join('\n')); console.log(`[+] Copied ${[...new Set(targets)].length} unique targets cleanly!`); }

## app a specific port at the end of app ips / domains ##

sed -i 's/$/:8015/' ip_with_no_8015.txt

## Copy the domain ##

copy([...new Set(document.body.innerText.match(/\b(?:[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?\.)+[a-zA-Z]{2,6}\b/g))].filter(d => !d.endsWith('.js') && !d.toLowerCase().includes('createelement')).join('\n')); console.log("[+] Unique domains copied to your clipboard!");
```
_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
