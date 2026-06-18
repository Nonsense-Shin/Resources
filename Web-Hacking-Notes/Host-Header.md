# The HTTP Host header is a mandatory request header as of HTTP/1.1. It specifies the domain name that the client wants to access

> The target URL is displayed either at the top of the panel (for Burp Repeater and Proxy interception) or on the "Target" tab in Burp Intruder. You can edit the target manually by clicking the pencil icon.

$ Check for flawed validation

*  GET /example HTTP/1.1
* `Host: vulnerable-website.com:bad-stuff-here`
___________________________________________________________________________
* GET /example HTTP/1.1
* `Host: hacked-subdomain.vulnerable-website.com`
___________________________________________________________________________________________________________________________________________________________
$ Inject duplicate Host headers

* GET /example HTTP/1.1
* `Host: vulnerable-website.com`
* `Host: bad-stuff-here`
___________________________________________________________________________________________________________________________________________________________
$ Add line wrapping

* GET /example HTTP/1.1
* `Host: bad-stuff-here`
* `Host: vulnerable-website.com`
___________________________________________________________________________________________________________________________________________________________

   - You can sometimes use `X-Forwarded-Host` to inject your malicious input while circumventing any validation on the Host header itself.
* GET /example HTTP/1.1
* `Host: vulnerable-website.com`
* `X-Forwarded-Host: bad-stuff-here`
___________________________________________________________________________________________________________________________________________________________

 - Although X-Forwarded-Host is the de facto standard for this behavior, you may come across other headers that serve a similar purpose, including:
* `X-Host`
* `X-Forwarded-Server`
* `X-HTTP-Host-Override`
* `Forwarded`
___________________________________________________________________________________________________________________________________________________________

                                                     *** Web cache poisoning via ambiguous requests ***
/*notice the verbose caching headers, which tell you when you get a cache hit and
how old the cached response is. Add an arbitrary query  parameter to your requests
to serve as a cache buster, for example, GET /?cb=123. You can change this parameter 
each time you want a fresh response  from the back-end server.*/

/*add a second Host header with an arbitrary value, this appears to be ignored when 
validating and routing your request. Crucially, notice that the arbitrary value of 
your second Host header is reflected in an absolute URL used to import a script*
