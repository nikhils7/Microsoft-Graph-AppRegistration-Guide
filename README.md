# Microsoft Graph App Registration Guide

This repository provides a step-by-step guide to register an Azure AD (Entra ID) application with certificate-based authentication for Microsoft Graph. It also includes instructions for generating a self-signed certificate and configuring PowerShell scripts for secure app-only authentication.

---

## 📋 What’s Included
- **AppRegistrationGuide.md** – Detailed steps to create an app registration and configure permissions.
- **SampleCertificateGuide.md** – How to generate a self-signed certificate using PowerShell.
- **LICENSE** – MIT License for open-source use.
- **.gitignore** – Recommended ignores for PowerShell projects.

---

## ✅ Why Certificate-Based Authentication?
- Secure app-only access without storing passwords.
- Ideal for automation and scheduled tasks.
- Works with Microsoft Graph PowerShell SDK.

---

## 🔑 Prerequisites
- Azure AD tenant and admin access.
- PowerShell 5.1+ installed.
- Microsoft Graph PowerShell SDK:
  ```powershell
  Install-Module Microsoft.Graph -Scope CurrentUser
