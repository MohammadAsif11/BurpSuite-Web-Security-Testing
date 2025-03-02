# BurpSuite-Web-Security-Testing

🔹 Step 1: Setting Up the Environment

1.1 Install Required Tools

✅ Download & Install Burp Suite Community/Professional from PortSwigger

✅ Install Mozilla Firefox or Google Chrome (for proxy configuration)

✅ Set up a test lab like:

DVWA (Damn Vulnerable Web App)

OWASP Juice Shop

WebGoat

1.2 Configure Burp Proxy

1️⃣ Open Burp Suite → Proxy → Options

2️⃣ Set 127.0.0.1:8080 as the listening proxy

3️⃣ Configure browser to use Burp Proxy

Firefox: Preferences → Network → Proxy → Set Manual Proxy (127.0.0.1:8080)

Chrome: Use FoxyProxy extension

4️⃣ Install Burp CA Certificate for HTTPS interception

Burp → Proxy → CA Certificate → Install in Browser

🔹 Step 2: Reconnaissance & Information Gathering

2.1 Identify Target Information

✅ Use Burp's Target Tab to discover subdomains & endpoints

✅ Gather:


Technology Stack (PHP, JavaScript, etc.)

Headers & Cookies

Hidden Input Fields

2.2 Passive Recon (Non-intrusive)

✅ Browse the website while Burp captures requests

✅ Use Burp Spider to map the application

✅ Identify API endpoints, authentication mechanisms, sensitive data exposure

🔹 Step 3: Active Scanning for Vulnerabilities

3.1 Use Burp Scanner (Professional Edition Only)

✅ Go to Target → Right-click → Actively Scan This Host

✅ Check for:

SQL Injection

XSS (Cross-Site Scripting)

CSRF (Cross-Site Request Forgery)

File Upload Vulnerabilities

Directory Traversal

🔹 Step 4: Manual Exploitation

4.1 Intercept & Modify Requests (Burp Proxy)

✅ Intercept login requests → Modify parameters (e.g., SQL Injection)

✅ Change User-Agent, Referrer, Cookies to test security controls

4.2 SQL Injection Attack (Burp Repeater)

✅ Capture a login request → Send it to Repeater

✅ Modify SQL query with:

sql

Copy

Edit

' OR 1=1 --

✅ Observe if authentication bypass occurs

4.3 XSS Injection (Burp Intruder)

✅ Inject payloads into form fields or URL parameters:

html

Copy

Edit

<script>alert('XSS')</script>

✅ Check if JavaScript executes

4.4 Brute Force Login (Burp Intruder)
✅ Capture a login request → Send it to Intruder
✅ Load a username/password list → Start brute force attack

🔹 Step 5: Testing APIs & Authentication
✅ Test Broken Authentication (session hijacking, weak tokens)
✅ Test API Endpoints (missing authentication, rate-limiting issues)
