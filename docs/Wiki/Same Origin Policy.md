---
tags:
  - web
---
**Same Origin Policy (SOP)** also called as **Single Origin Policy** is a security measure implemented in Web Browser programming languages such as JavaScript and AJAX and is one of the most fundamental concepts in the Web Application Security Model.

> It states that the Web Browser allows scripts contained in one web page to access the data or resources of another web page if and only if both the web pages have the **SAME ORIGIN**.

Origin is based on a number of parameters: 1. Protocol 2. Host Name 3. Port Number

SOP, originally made to protect access to the DOM is an important cornerstone of all browsers since 1995 and it prevents malicious scripts from one website from trying to access and manipulate sensitive date from another website through that page's DOM (Document Object Model).

Most modern websites use HTTP cookies to maintain authenticated user sessions and logins and in revealing sensitive information regarding the user and SOP plays a very significant role in such web applications. And it would have been very easy to steal this sensitive user data and session cookies for the attacker website's malicious scripts if this policy was not in place.

Lets see the practical implementation of this policy. Say that you have a social networking site opened with your account on one tab, and in another tab he/she has opened a website with a malicious Java Script Code that steals user login cookies from the browser. Lets assume that the SOP is currently not in place, then since the user is still actively using the social networking site with valid session cookies, the attacker can either steal those cookies, or can send requests on your behalf to that social networking site's server, while that server thinks that it is getting requests from the user, whereas you are not even aware of this. This can lead to serious problems and has a great potential as to how to hacker wants to manipulate the data. The attacker can read chats, send fake messages, post things from your account and do all sorts of illegal activities, and its really important that the web browser detects which JS is trusted to access the social networking site's data and which JS is untrusted. This is where Same Origin Policy comes into the picture and prevents the JS from accessing the social networking site's data.

SOP thus creates a kind of a sandbox that separates these websites from one another, and prevents the loss of data confidentiality and integrity and prevents client side attacks on the user.

Let us consider an example URL: `http://attack.example.com/dir/index.html`.

From the above URL, we can infer that the: 1. Protocol/Scheme: `http`  
2. Host: `attack.example.com`  
3. Subdomain: `attack`  
4. Domain: `example.com`  
5. Resource: `/dir/index.html`  
6. Directory: `/dir`  
7. File name: `index.html`

Here is how the Same-Origin-Policy works for the above URL.

| URL                                             | Outcome | Reason             |
| ----------------------------------------------- | ------- | ------------------ |
| `http://attack.example.com/dir/page.html`       | Success | Same origin        |
| `http://attack.example.com/dir/dir2/index.html` | Success | Same origin        |
| `http://ping.example.com/dir/index.html`        | Failure | Different host     |
| `http://example.com/dir/index.html`             | Failure | Different Host     |
| `http://attack.example.com:12/dir/index.html`   | Failure | Different Port     |
| `https://attack.example.com/dir/index.html`     | Failure | Different protocol |
