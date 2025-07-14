# 🔐 Authentication

All Hashlix API requests require authentication using an **API key**. This key uniquely identifies your account and is used to authorize access to the platform’s services.

---

## 📌 Where to Find Your API Key

You can generate and manage your API key(s) in your [Hashlix Dashboard](https://www.hashlix.com/dashboard):

1. Log in to your account.
2. Navigate to **Developers Menu**.
3. Click **API Keys**.
4. Enter the name of your API key and clicl **Create Key**.
5. Copy and securely store the key — you won’t be able to view it again.

> 🔒 Keep your API key secure and do not expose it in public repositories or client-side code.

---

## 🔧 How to Use Your API Key

Include your API key in the `Authorization` header of every request, using the **Bearer token** scheme.

### Example Header:

```http
Authorization: Bearer YOUR_API_KEY
```
