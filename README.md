Secure Software Development Project
Project Overview
This project demonstrates a full secure software development lifecycle applied to a deliberately
vulnerable Node.js + Express.js web application. The goal was to identify, exploit, fix, and verify security
vulnerabilities using both Dynamic Application Security Testing (DAST) and Static Application Security
Testing (SAST) techniques.
The project covers multiple vulnerability classes from the OWASP Top 10 and shows clear before / after
evidence of security improvements.
Team Members
2305187 – Mohamed Mohy El‑Din Abdel Latif
2305188 – Mahmoud Mohamed Gomaa
2305167 – Omar Mohamed Zoheir
Tools and Technologies Used
Node.js / Express.js – Target application environment
OWASP ZAP – Dynamic vulnerability discovery (DAST)
Postman – Manual exploitation and proof-of-concept (PoCs)
Semgrep – Static Application Security Testing (SAST)
Custom Semgrep Rules – Detection of project-specific vulnerability patterns
Git – Version control and security fix tracking
Project Phases
Phase 1: Dynamic Testing (DAST)
Automated scanning using OWASP ZAP
Manual exploitation using Postman
Discovery of 8+ real vulnerabilities
Mapping each vulnerability to OWASP Top 10 categories
Phase 2: Static Analysis (SAST)
Semgrep scan using built-in JavaScript and Node.js rules
Manual code review to locate vulnerable code
Creation of custom Semgrep YAML rules to detect exploited patterns
•
•
•
•
•
•
•
•
•
•
•
•
•
•
•
•
1
Phase 3: Fix and Hardening
Security issues were fixed directly in the source code, including: - Removal of hardcoded secrets and use of
environment variables - Input validation and output encoding - Secure JWT configuration (expiration, role
validation) - Proper authorization checks to prevent IDOR - Secure session and cookie configuration -
Protection against CSRF and Path Traversal attacks
Each fix was committed separately for clarity.
Phase 4: Re‑testing and Verification
Re-execution of the same attacks after fixes
Verification that exploits no longer work
Re-running Semgrep (built-in + custom rules)
Confirmation that security findings were resolved
Fixed Vulnerabilities Summary
Hardcoded Secrets
Reflected XSS
IDOR (Insecure Direct Object Reference)
JWT Misconfiguration
User Enumeration
CSRF
Session Fixation & Insecure Cookie Flags
Path Traversal
OTP Hardcoded Secret
All listed vulnerabilities were successfully fixed and verified.
Repository Structure
├── src/ # Application source code
├── semgrep-rules/ # Custom Semgrep YAML rules
├── .env.example # Environment variables template (no secrets)
├── README.md # Project documentation
├── Security_Project_Report.pdf
•
•
•
•
•
•
•
•
•
•
•
•
•
2
How to Run the Project
1. Clone the Repository
git clone https://github.com/SirAppSec/vuln-node.js-express.js-app.git
cd vuln-node.js-express.js-app
2. Install Dependencies
npm install
3. Configure Environment Variables
cp .env.example .env
Edit .env and add the required secrets.
4. Run the Application
npm run dev
The application will run locally on http://localhost:5000 .
Semgrep Usage
Run Built-in Rules
semgrep --config p/javascript --config p/nodejs
Run Custom Rules
semgrep --config semgrep-rules/
Deliverables
• Secure source code (GitHub repository)
3
Security_Project_Report.pdf (final version)
Custom Semgrep rules
Short demonstration video (exploit before / fix / exploit after)
Disclaimer
All testing was performed locally in a controlled lab environment for educational purposes only. No
external or real-world systems were targeted.
Final Result
The project successfully demonstrates how vulnerable code can be identified, exploited, fixed, and validated
using professional security tools and secure coding practices.
•
•
•
4# project-secure
