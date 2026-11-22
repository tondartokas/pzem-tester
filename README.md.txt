# ⚡ PZEM-004T v3 Web Serial Tester

A zero-dependency, bilingual (**Persian / English**) browser-based tool to test, configure, and monitor **PZEM-004T v3.0** AC energy meter modules directly from Windows/Desktop using the **Web Serial API** (no Python, Node.js, or backend required).

---

## ✨ Features / امکانات
- **Bilingual UI (FA / EN):** Instant switch between Persian (RTL) and English (LTR).
- **Direct COM Port Connection:** Connects via USB-to-TTL or USB-to-RS485 at `9600 baud, 8N1`.
- **Manual Slave Address:** Enter any address (`1–247`) or `248 (0xF8)` general address.
- **Bus Scanner:** Scan a range of Modbus addresses to discover connected PZEM modules and select them with one click.
- **Set Address:** Change a module's Modbus-RTU slave address (`Function 0x06`, Register `0x0002`).
- **Live Monitoring & Reset:** Read Voltage, Current, Power, Energy, Frequency, Power Factor, Alarm status, and Reset Energy (`0x42`).
- **Raw Hex Log:** View exact `TX` and `RX` Modbus RTU frames for hardware debugging.
- **Offline Windows App (PWA):** Installable via Microsoft Edge or Google Chrome to run standalone and offline.

---

## 🔌 Wiring / سیم‌کشی

> ⚠️ **Important:** The PZEM-004T v3 UART side is opto-isolated, and its internal metering IC is powered by the **220V AC mains input**. If 220V AC is not connected, the module will not respond (Timeout).

| USB-TTL Converter | PZEM-004T v3 |
| :---: | :---: |
| `5V` | `5V` |
| `GND` | `GND` |
| `TX` | `RX` |
| `RX` | `TX` |

---

## 🚀 How to Use / نحوه استفاده

1. Open the hosted **HTTPS** URL (GitHub Pages / Cloudflare Pages) in **Microsoft Edge** or **Google Chrome** on Windows.
2. Click **Select COM Port & Connect** and choose your USB-Serial converter.
3. Use **Scan Devices** if you don't know the module's current address, or enter `248` when only one module is connected.
4. *(Optional)* To install as a standalone offline Windows desktop app:
   - In **Microsoft Edge**: Click `...` (Menu) → **Apps** → **Install this site as an app**.
   - In **Google Chrome**: Click the **Install** icon in the address bar (or Menu → **Save and share** → **Install page as app**).

---

## 📁 Project Files
- `index.html` — Main UI and Modbus-RTU Web Serial logic
- `manifest.json` — PWA metadata for Windows desktop installation
- `sw.js` — Service Worker for offline caching
- `icon.svg` — Application icon
- `README.md` — Project documentation