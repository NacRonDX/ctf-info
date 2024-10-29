---
tags:
  - web
---
> HTTP cookies also called web cookies, internet cookies, browser cookies or simply as cookies. These are some kind of encoded form of text which is sent from the website. These are stored in the client system or the user's system. These do record every information that is done by the client like logging in clicking on some advertisement, adding something to the cart, and the pages visited by the client(the user). These are also used to remember the previously entered usernames, passwords, and some previously used card details

There are some kind of special cookies like authentication cookies so these are used for some authentication purposes, such that the user is logged in or not ,is that account is logged in in some other devices or not.T he security of the authentication is mainly dependent upon the cookie issued by the website and the level of encryption. Such that the vulnerabilities could make the hacker to read the cookies and gets the access to the data in the user's accounts

### How these can be misused
```
As of now many people who use the internet don't know the use of the cookies so these can be easily taken from them in so other ways, like so malicious scripts which would take your cookies just with one click. With these cookies, they can get all our login access and a chance of getting all our usernames and passwords and some sensitive information like our bank details.
```

### Types of Cookies
- [[#Session cookies]]
- [[#Persistent Cookies]]
- [[#Secure Cookies]]
- [[#Http-only Cookies]]
- [[#Same-site Cookies]]
- [[#Third-party Cookies]]
- [[#Super Cookies]]
- [[#Zombie Cookies]]

#### Session cookies
These cookies are also known as in-memory cookies, transient cookies, and non-persistent cookies. These exist only in temporary memory and while user travels forms one website to another website. These cookies will be deleted by the web browser after the user closes the web browser. These cookies do not have any type of expiry date or expiration time assigned to them, this is how the browser knows how to use session cookie

#### Persistent Cookies
As we know that session cookies don't have any time-related expiration time or some expiry date, but persistent cookies do have an expiry date so some length of time for expiration. So it means that as long as these cookies expire the cookie will be sending the data to the server as the client or the user uses visits the website or if the user uses the information belonging to the website from another website.

So these cookies or also called as _Tracking Cookies_ so these can be used by the advertisers to track the list of the sites visited by the user over a period of time. These are also used for the legitimate reasons (keep some logged in accounts to avoid the reentry of our credentials for every visit) _However these cookies would be rested after the expiration time or if it is deleted manually_.

#### Secure Cookies
These Secure cookies or transmitted only when the connections are secure so that these might no be captures while the connection was insecure (unencrypted connections). And these cookies are made more secure by adding some kind of Flag to the cookie.

#### Http-only Cookies
Http-only is the type of cookies that cannot be captured by the client-side API's. These restrictions do not allow the cookie theft via cross-site scripting (XSS) However these cookies are vulnerable to the cross-site tracing(XST) and cross-site request forgery(XSRF) attacks. A cookie is given this characteristic by adding the HttpOnly flag to the cookie.

#### Same-site Cookies
These cookies are introduced in Google version 51, called _Same-site cookies_ these cookies will only be sent in the request of the originating from the same origin to the target domain, so to restrict some types of attacks like cross-site request forgery. These cookies are given characteristic by setting the same-site flag to _Strict or Lax_.

#### Third-party Cookies
Normally a cookie's domain attribute will match the domain that is shown in the address bar of the web browser. These are called first party cookies. Whereas the third-party cookie belongs to a different domain that is shown in the address bar. This type of cookies will appear when a webpage contains some external contents from other websites such as advertisements or visiting their website. If we are using some website named xyz.com we will be having the cookies of xyz and an advertisement for some another website called abc.com. So it is eventually both these cookies are sent to the advertiser when loading or visiting their website. So the advertiser can use the cookies to know the browsing history of the user that have his advertisements from this advertiser.

Some years back some companies have set the cookies that are readable by 100 third-party domains. On an average website are setting 10 cookies with a maximum limit of 800 cookies

But the modern web browsers containing the privacy settings can block the third-party cookies.

#### Super Cookies
Super cookie is a cookie which is originated with the top level domains such as .com or for some public suffix such as .co .uk. But ordinary cookies have an origin of a specific domain name, such as abc.com.

These cookies are having some high-security concern and are therefore often blocked by the web browsers.In case if the web browser accepts the cookie and if the attacker is in control of the malicious website he could set a super cookie which would redirects the user to another website that shares the top level domain or public suffix as the malicious websites. For example, if a super cookie with an origin of .com could affect the request of the abc.com even if the cookie does not originate from abc.com.So that it can be used for the fake logins and change in the user information.

The public suffix helps to migrate the risks that super cookie could cause. The public suffix list cross-vendor initiative that aims to provide an accurate and up-to-date list of domain names and suffixes.
### Note
> This super cookie sometimes is also used for tracking purposes that do not relate to HTTP cookies. These mechanisms were found at Microsoft website in August 2011. Due to media attention, they disabled these cookies

#### Zombie Cookies
A zombie cookie is a piece of data usually used for tracking users, which is created by a web server while a user is browsing a website, and placed on the user's computer or other device by the user's web browser, similar to regular HTTP cookies, but with mechanisms in place to prevent the deletion of the data by the user. Zombie cookies could be stored in multiple locations—since failure to remove all copies of the zombie cookie will make the removal reversible, zombie cookies can be difficult to remove. Since they do not entirely rely on normal cookie protocols, the visitor's web browser may continue to recreate deleted cookies even though the user has opted not to receive cookies. 

Web analytics collecting companies use cookies to track Internet usage and pages visited for marketing research. Sites that want to collect user statistics will install a cookie from a traffic tracking site that will collect data on the user. As that user surfs around the web the cookie will add more information for each site that uses the traffic tracking cookie and sends it back to the main tracking server.

Zombie cookies allow the web traffic tracking companies to retrieve information such as previous unique user ID and continue tracking personal browsing habits. When the user ID is stored outside of a single browser's cookie storage, such as in a header injected by the network into HTTP requests, zombie cookies can track users across browsers on the same machine.

Zombie cookies are also used to remember unique IDs used for logging into websites. This means that for a user who deletes all their cookies regularly, a site using this would still be able to personalize to that specific user. 

### Useful extensions
[Edit this cookie](https://www.editthiscookie.com/)
