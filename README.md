# 🏕️ Camp Med Manager

> **⭐ Current version: `camp_mar.html`** — runs entirely in the browser on an iPhone, iPad, or any computer. No server or WiFi needed at camp. **iPhone/iPad require a one-time install step — see `SETUP_IPHONE.md`** (iOS won't run an HTML file opened directly from Files; it must be loaded from a URL once, then it works fully offline from the home screen). Supports 1 or 2 nurses (cabin split across two devices with an end-of-camp merge file), five-rights checks, controlled substance counts, PRN intervals, DYMO 30324 labels (content centered), and reconciliation/backup exports.
>
> Everything below describes the older Flask prototype, which requires a Mac to act as server.

A lightweight medication management app for summer camps. Runs locally on one Mac; all staff connect via browser on the same WiFi.

---

## Requirements
- macOS with Python 3 (pre-installed on all modern Macs)
- Flask (one install command below)
- Dymo Connect software (free from dymo.com) for label printing

---

## Setup (one time)

1. **Download and unzip** the camp_med folder anywhere (Desktop is fine)
2. Open **Terminal** (Spotlight → Terminal)
3. Install Flask:
   ```
   pip3 install flask
   ```
4. Navigate to the folder:
   ```
   cd ~/Desktop/camp_med
   ```
5. Start the app:
   ```
   python3 app.py
   ```

You'll see output like:
```
====================================================
  🏕️  Camp Med Manager
====================================================
  Local:    http://localhost:5000
  Network:  http://192.168.1.42:5000
  Share the Network URL with other staff
====================================================
```

6. Open `http://localhost:5000` on the host Mac, or share the **Network** URL with other staff on the same WiFi.

---

## Printing Labels

1. Make sure **Dymo Connect** is running on the Mac with the printer attached
2. Load **30334 labels** (2-1/8" × 2-3/4") in the Dymo
3. In the app, go to **Print Labels**, choose a date and pass, and click Print
4. When the print dialog opens, select your Dymo printer and click Print

**Tip:** In the print dialog, set paper size to "30334 Large Address" if it doesn't auto-detect.

---

## Stopping the app

Press `Ctrl+C` in the Terminal window. The database file (`camp_meds.db`) is saved in the same folder and persists between sessions.

---

## Data & Privacy

All data is stored locally in `camp_meds.db` — nothing leaves your network. Back up this file regularly.
