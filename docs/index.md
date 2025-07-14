# Welcome to the Hashlix API

Welcome to the official API documentation for [Hashlix](https://www.hashlix.com) — your trusted platform for mobile number decoding, bulk SMS, and WhatsApp messaging services. This documentation provides comprehensive technical reference for integrating our services into your systems.

---

## 🔍 What is Hashlix?

**Hashlix** is an all-in-one API platform built for businesses and developers that need:

- 🔓 **Hashed Number Decoding**: Instantly decode SHA256 or MD5 hashed mobile numbers into real phone numbers (if mapped).
- 📤 **Bulk SMS Delivery**: Seamlessly send SMS messages at scale with real-time delivery feedback.
- 🟢 **WhatsApp Messaging**: Send interactive and high-converting WhatsApp messages using verified templates.

Our platform supports flexible integrations via REST APIs.

---

## 🚀 Getting Started

To begin using the Hashlix API:

1. **Sign up** at [www.hashlix.com](https://www.hashlix.com).
2. Top up your account.
3. Generate an API Key from your dashboard.

Once you have your API key, include it in your headers to authenticate requests.

## 🌐 Base URL

All API endpoints are accessed via the following base URL:

**https://api.hashlix.com**

## 🧩 Available APIs

1. 🔓 Hash Decode API
   Convert SHA256 or MD5 hashes back into original phone numbers (if stored in our database).

    Endpoint: POST /decode/

    Rate: 1 credit per successful decode

    See Decode API Reference ›

2. 📤 Bulk SMS API
   Send high-volume SMS messages with optional personalization and scheduling.

    Endpoint: POST /sms/send/

    Rate: Based on destination network (e.g., Safaricom, Airtel)

    See SMS API Reference ›

3. 🟢 WhatsApp API
   Send interactive and high-converting WhatsApp messages using verified templates.

    Endpoint: POST /whatsapp/send/

    Rate: Based on destination network (e.g., Safaricom, Airtel)

    See WhatsApp API Reference ›

4. 📝 Email API
   Send bulk emails with personalized content and tracking.

    Endpoint: POST /email/send/

    Rate: Based on destination email provider (e.g., Gmail, Outlook)

    See Email API Reference ›

## 📈 Monitoring & Logs

You can track usage, delivery reports, and decode logs from the Analytics Dashboard.

## 🛠 Support

For questions, integration help, or service-specific guidance:

📧 Email: info@hashlix.com

💬 WhatsApp: +254 701 276 376

📘 Docs: docs.hashlix.com
