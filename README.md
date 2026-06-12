# 🧠 SC-Detect Core Backend Engine

![Django Version](https://img.shields.io/badge/Django-4.2.13-092E20?style=for-the-badge&logo=django&logoColor=white)
![DRF](https://img.shields.io/badge/DJANGO-REST-ff4646?style=for-the-badge&logo=django&logoColor=white)
![Security](https://img.shields.io/badge/HMAC--SHA512-Verified-blueviolet?style=for-the-badge)

The centralized backend platform powering the SC-Detect ecosystem. This engine processes high-performance asynchronous workloads, features a dual-consumer layout (Web & Mobile), and enforces strict fintech-grade security frameworks.

## 🏗 System Architecture & App Layout

The core is structured to decouple web presentation from mobile API ingestion points cleanly:

- `main/` — Global project configurations, routing tables, and security settings.
- `mobile_api/` — Stateless REST API endpoints exposed for mobile client integrations using secure Token Authentication.
- `website/` — Server-side rendered administration interfaces and analytical views.
- `postman/` — Pre-packaged integration test collections for API validation.

## 🛡 Advanced Engineering Implementations

### 1. Cryptographic Webhook Integrity Engine
To prevent transaction spoofing, the platform processes incoming financial/system callbacks using a strict `HMAC-SHA512` validation loop. It verifies parameters sequentially against system keys before state changes are authorized.

### 2. Custom Role-Based Access Control (RBAC)
Granular access control is handled via a custom `@allowed_groups()` decorator layer, allowing declarative view protection while seamlessly granting access to superusers.

### 3. Cross-Platform Dynamic Document Rendering
Includes a document compiler that dynamically formats HTML templates into downloadable A4 PDF reports, featuring pre-configured binaries for both Windows and Linux OS environments.

## 🚀 Local Installation & Deployment

### Prerequisites
- Python 3.10+
- `wkhtmltopdf` binaries installed to your local path.

### Bootstrapping the Server
1. Clone the repository and navigate to the backend folder:
```bash
   cd backend/SC-Detect-main
