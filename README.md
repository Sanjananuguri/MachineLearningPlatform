# ML Practice Platform – Secure E-Commerce-Style Learning

A secure, interactive, and scalable platform designed to help users practice real-world machine learning and data science problems in a LeetCode-style environment.

# Project Summary

The platform is a **web-based machine learning practice system** that simulates real-world scenarios and allows users to:
- Solve ML/Data Science/Analytics problems.
- Receive instant feedback.
- Purchase access to premium problems using Stripe payment.
- Interact in a secure environment protected with SSL and OTP-based multi-factor authentication.

Inspired by LeetCode, this platform bridges the gap between **academic knowledge** and **hands-on application**.

---

# Tech Stack

| Layer              | Technology Used          |
|-------------------|--------------------------|
| Frontend          | HTML, CSS, JavaScript    |
| Backend           | Node.js                  |
| Database          | MongoDB                  |
| Hosting           | **AWS EC2 Instance**     |
| Payment Gateway   | Stripe                   |
| Authentication    | Email OTP + SSL          |
| Deployment        | Node.js Server on AWS with SSL |

---

# AWS Hosting

- The entire application is deployed on **AWS EC2** for production.
- **SSL/TLS certificate** implemented to enable secure HTTPS connections.
- AWS was used to:
  - Host the Node.js backend
  - Serve the front-end HTML/CSS pages
  - Manage domain and DNS configurations (via Route 53 if applicable)
- Elastic IPs and security groups were configured to manage traffic securely.

---

# Security Features

- **Multi-factor authentication** using Email OTP
- **SSL/TLS encryption** for secure data transmission
- **Vulnerability assessments** using Qualys WAS and Hosted Scan
- Security header evaluations and recommendations applied:
  - `Strict-Transport-Security`
  - `Content-Security-Policy (CSP)`
  - `X-Frame-Options`
  - `X-Content-Type-Options`

---

# Vulnerability Assessment Highlights

- ✅ No critical or high-risk vulnerabilities detected
- ⚠️ 20 medium-level findings (mostly Level 3 severity)
- 🔐 No sensitive content exposed
- 🧼 Recommendations implemented:
  - Upgraded to TLS 1.2/1.3
  - Added modern security headers
  - Strengthened XSS and clickjacking protection

---

# Key Features

- User authentication with OTP
- Free + premium problem-solving model
- Secure Stripe payment integration
- Real-time feedback and tracking
- Admin-controlled problem deployment
- MongoDB-backed analytics and data management

---

# Deployment Architecture

```mermaid
graph LR
  A[User Browser (HTTPS)] --> B[AWS EC2 Instance]
  B --> C[Node.js Server]
  C --> D[MongoDB (Database)]
  C --> E[Email Server (OTP)]
  C --> F[Stripe Payment Gateway]

  B -.-> G[SSL/TLS Layer for Secure Communication]

