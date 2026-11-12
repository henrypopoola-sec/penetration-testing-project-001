# Phase 3: Web Reconnaissance

## 1. Objective

To investigate publicly accessible web resources on scanme.nmap.org using HTTP requests and basic web reconnaissance techniques.

## 2. Tools Used

- Termux
- curl
- grep
- Nmap

## 3. HTTP Header Investigation

Command executed:

curl -I http://scanme.nmap.org

### Findings

- HTTP Status: 200 OK
- Web Server: Apache/2.4.7 (Ubuntu)
- Content Type: text/html
- Accept-Ranges: bytes

### Interpretation

The server successfully processed the HTTP request and disclosed its web server software and version through the Server header.

## 4. HTML Inspection

Command executed:

curl -s http://scanme.nmap.org | head -n 15

### Findings

- Page title: Go ahead and ScanMe!
- JavaScript resource: /shared/js/nst.js
- CSS resources identified.
- Google Analytics reference observed.

### Interpretation

The HTML source exposed publicly accessible resource paths and information about the website's frontend structure.

## 5. JavaScript Investigation

Command executed:

curl -I http://scanme.nmap.org/shared/js/nst.js

### Findings

- HTTP Status: 200 OK
- Content Type: application/javascript
- Content Length: 2235 bytes
- Last Modified: 2 May 2023

The JavaScript source contained:
- A debounce function.
- Menu interaction functions.
- Event listeners.

## 6. Sensitive Keyword Search

Command executed:

curl -s http://scanme.nmap.org/shared/js/nst.js | grep -Ein 'api[_-]?key|secret|password|token|admin'

### Result

No matching keywords were found.

### Interpretation

The search did not identify the specified keywords in the inspected JavaScript file. This does not establish that the entire file or website is free from sensitive information.

## 7. Limitations

- Investigation was limited to publicly accessible resources.
- No exploitation was attempted.
- No authentication bypass was attempted.
- No vulnerability was confirmed.

## 8. Lessons Learned

- HTTP response header analysis.
- HTML source inspection.
- JavaScript resource enumeration.
- Basic JavaScript code interpretation.
- Searching for potentially sensitive strings.
- Distinguishing reconnaissance observations from confirmed vulnerabilities.

## 9. Conclusion

The exercise demonstrated how publicly accessible web resources can reveal information about a website's server, frontend structure and JavaScript functionality.

These findings provide a foundation for further authorized web security assessments.
