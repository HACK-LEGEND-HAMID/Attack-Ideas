# CURL. The Hacker's First Recon Tool.

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

### A Simple Checklist

Found `/admin/`. Try to access it. Maybe it loads a login page. Maybe it loads the dashboard directly without asking for a password.

Found `.env`. Download it. Look for DB_PASSWORD, API_KEY, SECRET, TOKEN.

Found `config.php.bak`. Download it. Read the database credentials.

Found `database.sql`. Download it. Import it locally. Browse every table.

Found `.git/`. Clone the repository. Read the commit history. Find secrets that were committed and later removed.

Found `robots.txt`. Read it carefully. Visit every path listed under Disallow. Those are the paths the owner never wanted you to see.

### What Hurts The Most

An exposed `.env` file is critical because it gives database access. A downloadable `database.sql` file is critical because it exposes every user's data. An accessible `.git` folder is critical because it reveals the complete source code. An open `/admin/` panel is highly dangerous because it hands over website control. A browsable `/backup/` folder is dangerous because old files contain unfixed vulnerabilities.
This was just the first command. No flags. No tricks. Just `curl`.
There is a lot more to learn. Headers. Cookies. Sending data. Faking your identity. Every flag does something different.
Keep going. The good stuff is next.
