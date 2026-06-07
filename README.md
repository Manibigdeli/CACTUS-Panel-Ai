<div align="center">
  
# Project Nahan (پروژه نهان)
### The Ultimate Serverless Gateway on Cloudflare Workers

**Nahan** (Persian for *Hidden/Concealed*) is a secure, lightweight, and highly customizable reverse proxy running entirely on the Edge. It transforms your Cloudflare Worker into a powerful, obfuscated gateway using VLESS or Trojan protocols, managed via a beautiful, self-contained Web UI.

[![Cloudflare Workers](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white)](https://workers.cloudflare.com/)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)
[![Version](https://img.shields.io/badge/Version-2.0-0A66C2?style=for-the-badge)]()

</div>

---

## 🌟 Why Nahan?

Nahan isn't just a proxy script; it's a complete management solution designed for stealth, speed, and ease of use.

*   🛡️ **Hidden in Plain Sight:** Unauthorized access attempts are seamlessly proxied to legitimate sites (like `ubuntu.com` or `docker.com`), making your server look like a regular website to scanners.
*   ⚡ **Zero Server Cost:** Runs entirely on Cloudflare's Free Tier. No VPS, no server maintenance, just code.
*   🎨 **Modern Dashboard:** A fully embedded, mobile-friendly dashboard with Dark/Light modes and Dual-Language support (English/فارسی).
*   🤖 **Telegram Bot Integration:** Manage your gateway, check usage, and receive login alerts directly via Telegram.
*   📡 **Multi-User & Multi-IP:** Generate unique subscription links for different users (Profiles) and automatically multiply configs across multiple Clean IPs.

## ✨ Key Features

| Feature | Description |
| :--- | :--- |
| **🔐 Dual Protocol** | Switch instantly between **VLESS** (Alpha) and **Trojan** (Beta) modes. |
| **📱 QR Code Generation** | Beautiful modal-based QR codes for instant mobile configuration. |
| **👥 Multi-Sensor Profiles** | Create separate profiles (`uuid:name`) with unique subscription links for different users. |
| **🌍 Clean IP Multiplexer** | Input a list of Clean IPs, and Nahan automatically generates subscription configs for all of them. |
| **⚙️ Real-Time Metrics** | View Origin IP, Edge Node location, and run browser-side latency diagnostics. |
| **💾 KV State Storage** | Configuration persists in Cloudflare KV (`IOT_DB`) even after code updates. |
| **🚨 Kill Switch** | Immediately pause all proxy traffic with one click from the dashboard or Telegram. |

## 🚀 Quick Start

Get your gateway running in under 2 minutes.

### 1. Create a KV Namespace
1. Go to **Cloudflare Dashboard** → **Workers & Pages** → **KV**.
2. Create a namespace named `IOT_DB`.

### 2. Deploy the Worker
1. Go to **Workers & Pages** → **Create Application** → **Create Worker**.
2. Name your worker (e.g., `nahan-core`) and click **Deploy**.
3. Click **Edit code**, paste the Nahan script, and save.

### 3. Bind Storage
1. Go to your Worker → **Settings** → **Bindings**.
2. Under **KV Namespace Bindings**, add:
   *   **Variable name:** `IOT_DB`
   *   **KV namespace:** Select the namespace you created.
3. Save and Redeploy.

### 4. Access & Configure
1. Open `https://<your-worker>/sync/dash`.
2. Login with the default key: `admin`.
3. Configure your UUID, Clean IPs, and Protocols.

> **⚠️ Important:** Change the default Master Key in the **System** tab immediately after logging in.

## 📖 Documentation

For a full breakdown of dashboard features, check out the [User Guide](HELP.md).

---

<div align="center">
Made with ❤️ by the Open Source Community
</div>
