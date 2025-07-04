# Granting Secure Token via Jamf Self Service

This guide is to assist users in granting themselves a **Secure Token** using a Jamf Self Service policy. This is required to enable macOS updates and reinstalls using tools like `erase-install`.

---

## 🎯 Goal

Enable a user to receive a Secure Token using a Jamf Self Service policy.

---

## ✅ Prerequisites

- The Mac is enrolled in **Jamf Pro** via **Automated Device Enrollment (ADE)**.
- A **Bootstrap Token is escrowed** to Jamf.
- A **Secure Token-enabled admin account** exists (e.g., created via MDM).
- The user is **logged in locally** to their Mac.
- You have access to the **admin password**

---

## 👨‍💻 Step-by-Step Instructions

### 1. Contact the User
- Let them know you’ll help enable macOS updates on their Mac.
- Ask them to stay logged in and open **Jamf Self Service**.

### 2. Guide the User to Run the Policy
- Instruct them to search for and click on:
  > **“Enable macOS Updates”** (or the name of the policy)

### 3. Explain the Prompts
- The user will be prompted to enter their **Mac password**.
- You (the technician) will be prompted to enter the **admin password**.
- Reassure the user that their password is **not stored or logged**.

### 4. Wait for Confirmation
- If successful, the user will see a message confirming Secure Token was granted.
- If it fails, a message will instruct them to contact IT.

### 5. (Optional) Log Review
- The script logs results to:
  `/var/log/secureTokenGrant.log`

---

## 🔐 Security Notes

- Passwords are collected securely using AppleScript dialogs.
- No passwords are stored or written to disk.
- Only success/failure messages are logged.
