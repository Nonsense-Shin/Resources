### Just some out of the Box logics to mess with. ###
(This is just basic out of the box thiking you should think and develop further yourslef.)

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
***UPDATE: LOGIC FLAWS ARE EVERYWHERE AND THIS MARKDOWN FILE IS FROM WHEN I STARTED OUT, AT THE MOMENT THE AMOUNT OF LOGIC FLAWS I HAVE ENCOUNTERED IS VERY VAST. USE THIS AS A REFERENCE IF YOU'RE JUST STARTING OUT***
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

//Excessive trust in client-side controls (poor backend)
`just mess around with the backend`

//2FA (2 Factor Authorization) broken logic / bypass

 - bruteforce might be a valid option,
   * take the seesion token after that
   * try: When prompted for the verification code, manually change the URL 
   * to navigate to specific endpoints`
_______________________________________________________________________________________________________________________________
//Failing to handle unconventional input
* supply negatives
*  things that aren't meant to be understood by the logic
* create pure anomaly and lookout for bugs
* Insane amounts or requests`
_______________________________________________________________________________________________________________________________
//Inconsistent handling of exceptional input
- Try random attacks null byte payloads and bug the system :
add very-long-strings atleast 200 characters long`
_______________________________________________________________________________________________________________________________
//Password reset broken logic
- try to reset/ delete password apply proxy and try things`
_______________________________________________________________________________________________________________________________
//Inconsistent security controls
- chaange your phone, number, email to something you don't have access to 
- even better find out someone else's and try out theirs,
- reuse coupons; when failing try different things maybe alternate betn the coupons...
- got one coupon? well try to get some more, maybe same way maybe a workaround`
_______________________________________________________________________________________________________________________________
//Weak isolation on dual-use endpoint
- proxy requests modify some, delete some and play around with it
- check which coding appears to bypass the server's validation`
_______________________________________________________________________________________________________________________________
//login
 * without auth"
 * weak backend"
 * exif data"

           ***Trusted users won't always remain trustworthy***
