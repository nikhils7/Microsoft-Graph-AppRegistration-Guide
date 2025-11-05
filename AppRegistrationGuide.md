
# How to Register an Azure AD App with Certificate Authentication for Microsoft Graph

This guide explains how to set up an Azure AD (Entra ID) app registration with certificate-based authentication for use with Microsoft Graph PowerShell SDK.

---

## ✅ Why Use Certificate-Based Authentication?
- Secure app-only access without storing passwords or secrets.
- Ideal for automation scripts and scheduled tasks.

---

## 📋 Prerequisites

1. **Microsoft Graph PowerShell SDK** installed:
   ```powershell
   Install-Module Microsoft.Graph -Scope CurrentUser
   ```

2. **Azure AD Access** with permissions to create app registrations and grant admin consent.

---

## 🛠️ Steps to Register the App

### 1. Create App Registration
- Go to [Azure Portal](https://portal.azure.com)
- Navigate to **Entra ID → App registrations → New registration**
- Name the app (e.g., `GraphAutomationApp`)
- Supported account types: **Single tenant**

### 2. Upload Certificate
- Go to **Certificates & secrets → Certificates**
- Upload a `.cer` or `.pem` certificate
- Save the **Thumbprint**

### 3. Assign API Permissions
- Go to **API permissions → Add a permission → Microsoft Graph → Application permissions**
- Add:
  - `User.Read.All`
  - `Directory.Read.All`
  - `Mail.Send`
- Click **Grant admin consent**

### 4. Get Required IDs
- **Tenant ID**: Found in Azure AD → Overview
- **Client ID**: Found in App registration → Overview

---

## ⚙️ Script Configuration
Update these placeholders in your PowerShell script:
```powershell
$TenantId   = '<YOUR-TENANT-ID>'
$ClientId   = '<YOUR-APP-CLIENT-ID>'
$CertThumb  = '<YOUR-CERT-THUMBPRINT>'
$Sender     = '<SENDER-EMAIL>'
$Recipient  = '<RECIPIENT-EMAIL>'
```

---

## 🔐 Security Notes
- Never share your certificate or private key publicly.
- Use secure storage like **Azure Key Vault** for production environments.
- Keep your app registration limited to only required permissions.

---

## 📂 Recommended Files to Include in Your Repo
- `DisabledUsersReport.ps1` – Your main script
- `README.md` – Instructions and prerequisites
- `LICENSE` – MIT license
- `.gitignore` – To exclude logs, CSVs, and temp files
- `AppRegistrationGuide.md` – This guide

---

## 👤 Author
Nikhil Sawant – IT Senior Analyst
