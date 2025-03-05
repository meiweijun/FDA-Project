# FDA Part 11 Compliant Electronic Signature Approval Workflow

[![Power Platform](https://img.shields.io/badge/Power_Platform-OK-green)](https://powerplatform.microsoft.com/)
[![Azure Functions](https://img.shields.io/badge/Azure_Functions-v4-blue)](https://azure.microsoft.com/services/functions/)
[![License](https://img.shields.io/badge/License-MIT-orange)](LICENSE)

A secure, auditable, and FDA Part 11-compliant electronic signature approval workflow built on Microsoft Power Platform. This solution ensures **data integrity**, **non-repudiation**, and **regulatory compliance** for critical processes in life sciences and regulated industries.

---

## 📜 Features

### **FDA Part 11 Compliance**
- **Electronic Signature Binding**  
  Digitally binds signatures to approval records using SHA-256 hashing.
- **Audit Trail**  
  Tracks user actions (submission/approval/rejection) with timestamps, IP addresses, and user context.
- **Data Integrity**  
  Immutable storage of approval records as PDF/A files with cryptographic hashes.
- **Access Control**  
  Enforces Azure AD authentication and role-based permissions.

### **Core Functionality**
- **Signature Capture**  
  Pen-based signature input via Power Apps (`PenInput` control).
- **Document Management**  
  Securely upload and store documents in SharePoint with version control.
- **Automated Workflow**  
  Power Automate orchestrates approval routing, notifications, and compliance checks.
- **Tamper-Evident Storage**  
  Approval records hashed and stored in SharePoint/Azure Blob Storage.

---

## 🛠️ Architecture

```mermaid
graph TD
  A[Power Apps UI] -->|Submit Document + Signature| B[Power Automate]
  B -->|Generate SHA-256 Hash| C[Azure Function]
  C -->|Store Metadata| D[SharePoint List]
  B -->|Create PDF/A| E[Adobe PDF Services]
  E -->|Immutable Storage| F[Azure Blob Storage]
  B -->|Audit Log| G[Azure SQL]
  H[Microsoft Graph] -->|User Validation| B
```
## 🚀 Getting Started
**Prerequisites**



