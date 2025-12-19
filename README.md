# Vulnerable Node.js Express Application

This repository contains a deliberately vulnerable Node.js + Express application used for
security testing and analysis with tools such as **OWASP ZAP** and **Semgrep**.

---

## Prerequisites

Make sure you have the following installed:

- Git
- Node.js (v16+ recommended)
- npm
- OWASP ZAP
- Semgrep

---

## Installation and Running the Server

Clone the repository and install dependencies:

```bash
git clone https://github.com/SirAppSec/vuln-node.js-express.js-app.git
cd vuln-node.js-express.js-app
npm install
npm install nodemon
Start the development server:

bash
Copy code
npm run dev
The application will be available at:

arduino
Copy code
http://localhost:5000
Running OWASP ZAP
Start OWASP ZAP:

bash
Copy code
zap.sh
Automated Baseline Scan
bash
Copy code
zap-baseline.py -t http://localhost:5000
Performs passive scanning only

Safe for quick vulnerability discovery

Full Active Scan
bash
Copy code
zap-full-scan.py -t http://localhost:5000
Performs active attacks

Use only in a test environment

Running Semgrep
Semgrep with Base Rules
Run official JavaScript and Node.js security rules:

bash
Copy code
semgrep --config p/javascript --config p/nodejs --error
Semgrep with Custom Rules
Run all custom rules located in the semgrep-rules directory:

bash
Copy code
semgrep --config semgrep-rules/
Custom rules are used to detect application-specific vulnerabilities such as:

Path Traversal

Hardcoded JWT secrets

Open Redirects

XSS patterns
