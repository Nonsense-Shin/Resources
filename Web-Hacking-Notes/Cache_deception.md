
# A static web page is one that:
 - Is pre-built and stored on the server as is (usually .html, .css, .js files)
 - Does not change based on who’s visiting or what they’re doing
 - Is served exactly the same to every user, every time

"Focus on endpoints that support the `GET`, `HEAD`, or `OPTIONS` methods"
__________________________________________

## Caches may have rules based on specific static extensions.
 - Try a range of extensions including:
    Cache File Types: -
    `.js, .css, .jpg, .jpeg, .png, .gif, .svg, .woff, .ttf,
                       .mp4, .mp3, .ico, .wasm, .exe `


- Common cache-phrase :   `-X-Cache   -X-Cache-Lookup   -Cache-Control    -Age
                          -Expires   -cf-cache-status    -Fastly-Cache      
                          -X-Proxy-Cache     -X-Drupal-Cache `
       
- Common static page directories: /static, /assets, /scripts /images /resources
      
`note: cache key is the request line & dynamic cache means no cache`
__________________________________________

sometimes the server caches data in /abc/../resource format and something quite the alternative
such as /resource/../abc '
- here `static` is the "static directory" and `abc` is the page (myaccount/profile/whatever)

__________________________________________

#"Some things to keep in mind."#

$ NULL byte = %00 [OpenliteSpeed {might not work sometimes}, Akamai , Fastly(CDNs)]
                                            /profile%00 = profile

$ Encoded slash = %2F [NGINx, (may work in akamai/cloudfront but rarely)]
                         /api%2Fv1 = api/v1

$ Semi-Colon = ; [apache, tomcat, fastly, cloudflare]
                        /index.php;a=b = /index.php

$ Query and Fragement = ? and # [ cloudflare, akamai ]
 
                             
$ Tab and space encoding = %09 and %20 [ akamai ]
                           /path%20image.js = /path image.js

$ Double Slash = // [ mostly many ]
                         /path//image.png = /path/image.png

__________________________________________

 FILES LIKE THESE :robots.txt, index.html, favicon.ico ARE SUPER HELPFUL IF THE SERVER SERVES THESE
 
 'for example you can try one of these and the server might cache it'

- cache control is green flag

- X-Cache
- X-Cache: hit 
- X-Cache: miss

- dynamic cache is red flag

- X-Cache: dynamic

- no store value is red flag
- no cache is red flag

*If you want to do automated testing : https://github.com/Hackmanit/Web-Cache-Vulnerability-Scanner is a great resource*
