### Exploiting an API endpoint using documentation

- *If you get any `/api` parameter abuse it to the fullest*
- *Break it down to the smallest bit*
___________________________________________________________________________________________________________
### L**ook for patterns that suggest API endpoints in the URL structure, such as / `api`**

- *Try every combination of attacks on /api parameter*
- *Try changing `HTTP` methods like `GET` `POST` `OPTIONS` `DELETE` `PATCH` and so many more...*
___________________________________________________________________________________________________________
### Identify / Find / Access API documentations…
*API behave differently depending on the content type of the data provided in a request.
Changing the content type may enable you to…*

- *[To change the content type, modify the `Content-Type` header,]*
- *Trigger errors that disclose useful information.*
- *Bypass flawed defenses.*
    - *gitTake advantage of differences in processing logic.For example:
    'an API may be secure when handling JSON data '
    'but susceptible to injection attacks when dealing with XML.'*
___________________________________________________________________________________________________________
### Find and exploit an unused API endpoint

- *Find the api requests*
- *Try changing the methods to find out the vuln*
- *Try playing without registration and then register*
- *Play around with sessions with non-registered requests*
- *Try to see the bodies of different request and response (look for json structures*)
___________________________________________________________________________________________________________
### Identify hidden parameters

- *" /id/ /isAdmin/ anything "*
- *abuse contents found after the sessions with without session requests*
- *if you find parameter not found/ not supported something like that then abuse it*
___________________________________________________________________________________________________________

### "Analyzing the responses is always a great idea" ###
___________________________________________________________________________________________________________
