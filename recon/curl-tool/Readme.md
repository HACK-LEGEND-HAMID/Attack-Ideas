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

## One Last Thing.

`curl -I` is a head request. It is fast. It is silent. It does not download anything large. It gives you the blueprint of the server before you even touch the front door.

Use it first. Use it always. Let the headers guide your next move.
