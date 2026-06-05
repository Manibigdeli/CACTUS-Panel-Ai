# Project Nahan (نهان) - User Walkthrough

This guide will walk you through accessing and managing your deployed Nahan gateway.

## 1. Accessing the Dashboard

By default, your dashboard is mapped to the `/sync/dash` route. 
To access it, open your browser and navigate to:
`https://<YOUR_WORKER_DOMAIN>/sync/dash`

*(Note: If you visit the root domain or `/sync` via a web browser, the system will camouflage itself and show the specified maintenance websites to redirect network scanners).*

## 2. Authentication

When you open the dashboard, you will be greeted by the gateway login screen.
*   **Default Master Key:** `admin`
*   Enter your key and click **Authenticate**.

*(If you see a warning saying "⚠️ DB sync missing!", it means you have not bound the `IOT_DB` KV namespace to your worker. Return to Cloudflare settings to bind it before attempting to save configuration updates).*

## 3. Using the Dashboard

The dashboard consists of 4 main tabs:

### 📡 Endpoints (Info)
This is where you retrieve your connection strings to import into your client application.
*   **Direct Stream Link:** The direct URI format (VLESS or Trojan based on active mode). You can scan the generated QR code using your mobile device.
*   **Cloud Sync URL:** The base API path for direct Sub/Config syncing.

### 📊 Metrics (Network)
Displays network properties regarding the processing Cloudflare edge node.
*   **Network Cards:** View Origin IP, executing Edge Node (Colo), and Regional data.
*   **Latency Diagnostics:** Enter your clean IP list in the Advanced tab and run real-time fetch requests directly from your browser to measure actual routing latency.

### ⚙️ System (Settings)
Configure core gateway profiles:
*   **Primary Display Mode:** Toggle between `Alpha Mode` (VLESS) and `Beta Mode` (Trojan).
*   **Device UUID:** Your connection identifier/password. Leaving this blank causes the system to auto-generate one based on your path.
*   **API Route:** Change this from `sync` to a hidden keyword (e.g., `my-secret-path`). Your dashboard will dynamically move to `/my-secret-path/dash`.
*   **Master Key:** Change the dashboard login password from `admin` to a secure custom passphrase.
*   **Backup & Restore:** Export your current dashboard parameters to a local `.json` file, or import a previously saved backup file to populate all inputs instantly.

### 🌐 Advanced (Network)
Fine-tune transport properties:
*   **Clean IPs:** Input your preferred clean Cloudflare IPs (one per line). The subscription generator will automatically multiply profiles using these endpoints.
*   **Resolver IP:** Set custom DNS resolution parameters for connection routing.
*   **Maintenance Hosts:** A comma-separated list of websites (e.g., `www.ubuntu.com, www.docker.com`). Unauthorized users scanning your domain will be proxied to these sites.
*   **TCP Fast Open (TFO):** Toggle TCP Fast Open flags inside the configuration profiles.
*   **Secure Hello (ECH):** Toggle Encrypted Client Hello parameters in client configurations.

## 4. Applying Changes

After adjusting any inputs in the **System** or **Advanced** tabs:
1. Click the **Update Config** button at the bottom of the screen.
2. The indicator will show "Syncing..." and then reload automatically.
3. *Important:* If you changed the **API Route**, the page will automatically redirect you to the new URL (e.g., `/<new-route>/dash`). Please bookmark the new link for future access.
