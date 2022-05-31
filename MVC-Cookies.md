# Cookies

![](cookie.png)

A cookie is basically a physical, plain-text file stored by the client (usually a browser), tied to a specific website. The client will then allow this specific website to read the information stored in this file on subsequent requests, basically allowing the server (or even the client itself) to store information for later use.

send a cookie to the client

```
HttpContext.Response.Cookies.Append("user_id", "1");
```


### HTTP cookies

An HTTP cookie (web cookie, browser cookie) is a small piece of data that a server sends to a user's web browser. The browser may store the cookie and send it back to the same server with later requests. Typically, an HTTP cookie is used to tell if two requests come from the same browser—keeping a user logged in, for example. It remembers stateful information for the stateless HTTP protocol.

### Cookies are mainly used for three purposes

1- Session management

Logins, shopping carts, game scores, or anything else the server should remember

2- Personalization

User preferences, themes, and other settings

3- Tracking

Recording and analyzing user behavior

### The Set-Cookie HTTP response header sends cookies from the server to the user agent. A simple cookie is set like this

Set-Cookie: \<cookie-name>=\<cookie-value>

```
HTTP/2.0 200 OK
Content-Type: text/html
Set-Cookie: yummy_cookie=choco
Set-Cookie: tasty_cookie=strawberry
```

### Define the lifetime of a cookie

The lifetime of a cookie can be defined in two ways

1- Session cookies are deleted when the current session ends. The browser defines when the "current session" ends, and some browsers use session restoring when restarting. This can cause session cookies to last indefinitely.

2-Permanent cookies are deleted at a date specified by the Expires attribute, or after a period of time specified by the Max-Age attribute.

### Restrict access to cookies

A cookie with the Secure attribute is only sent to the server with an encrypted request over the HTTPS protocol.

```
Set-Cookie: id=a3fWa; Expires=Thu, 21 Oct 2021 07:28:00 GMT; Secure; HttpOnly
```

### The expires option

Each of the options after the cookie value are separated by a semicolon and space and each specifies rules about when the cookie should be sent back to the server. The first option is expires, which indicates when the cookie should no longer be sent to the server and therefore may be deleted by the browser. The value for this option is a date in the format Wdy, DD-Mon-YYYY HH:MM:SS GMT such as:

```
Set-Cookie: name=Nicholas; expires=Sat, 02 May 2009 23:38:25 GMT
```

### Domain attribute

The Domain attribute specifies which hosts can receive a cookie. 

### Path attribute

The Path attribute indicates a URL path that must exist in the requested URL in order to send the Cookie header.

### SameSite attribute

The SameSite attribute lets servers specify whether/when cookies are sent with cross-site requests (where Site is defined by the registrable domain and the scheme: http or https).

```
Set-Cookie: mykey=myvalue; SameSite=Strict
```

### Cookie prefixes

__Host

If a cookie name has this prefix, it's accepted in a Set-Cookie header only if it's also marked with the Secure attribute, was sent from a secure origin, does not include a Domain attribute, and has the Path attribute set to /. This way, these cookies can be seen as "domain-locked".

__Secure

If a cookie name has this prefix, it's accepted in a Set-Cookie header only if it's marked with the Secure attribute and was sent from a secure origin. This is weaker than the __Host- prefix.

### Automatic cookie removal

There are a few reasons why a cookie might be automatically removed by the browser

Session cookies are removed when the session is over (browser is closed).

Persistent cookies are removed when the expiration date and time have been reached.

If the browser’s cookie limit is reached, then cookies will be removed to make room for the most recently created cookie.


### Subcookies

Due to the cookie number limit, developers have come up with the idea of subcookies to increase the amount of storage available to them. Subcookies are name-value pairs stored within a cookie value and typically have a format similar to the following

```
name=a=b&c=d&e=f&g=h
```

### HTTP-Only cookies

Microsoft introduced a new option for cookies in Internet explorer 6 SP1: HTTP-only cookies. The idea behind HTTP-only cookies is to instruct a browser that a cookie should never be accessible via JavaScript through the document.cookie property.

```
Set-Cookie: name=Nicholas; HttpOnly
```
