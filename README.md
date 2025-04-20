# 🚀 SlotSniper: TrafficBypass-Pro Dev Toolkit

## Built for Cybersecurity Enthusiasts🛡️💻

## 📘 Overview

When LMS slot portals crash at 9 PM due to massive traffic, most students give up. But not you. This toolkit turns you into a ghost in the system — faster, stealthier, and unstoppable.

With SlotSniper, you can:
- **Bypass server traffic**
- **Automate booking** with various techniques
- **Analyze APIs** for optimized booking
- **Launch parallel ghost attempts**
- **Simulate and handle error codes**
- **Ethically emulate a low-scale DoS attack**
- **Snipe slots from mobile** using Termux and VPNs


## 🛠️ Setup Checklist

### 1. Install Required Packages

To get started, you need to install the following dependencies:

```bash
# Install requirements for Python scripting
pip install requests
pip install selenium playwright

# For Termux (mobile use)
pkg install python
```

## Methods & Scripts
### Method 1: Python Auto-Retry Sniper Script
This script attempts to book the slot multiple times and retries if an error occurs.
```
import requests
import time

# Define URLs for different types of bookings
booking_urls = {
    "viva": "https://lms2.ai.saveetha.in/api/book_viva",
    "cia": "https://lms2.ai.saveetha.in/api/book_cia",
    "reep": "https://lms2.ai.saveetha.in/api/book_reep",
    "module": "https://lms2.ai.saveetha.in/api/book_module"
}

# Function to select the booking type
def get_booking_url(booking_type):
    return booking_urls.get(booking_type.lower(), None)

# Booking details (you can modify this to get dynamically from the page)
data = {"slot_id": "123", "student_id": "your_id"}
headers = {
    "Authorization": "Bearer your_token",
    "Content-Type": "application/x-www-form-urlencoded"
}

def book_slot(booking_type):
    url = get_booking_url(booking_type)
    if url is None:
        print("Invalid booking type selected.")
        return
    
    for i in range(50):
        try:
            res = requests.post(url, data=data, headers=headers)
            print(f"Attempt {i+1} => {res.status_code}")
            if res.status_code == 200:
                print("✅ BOOKED!")
                break
        except Exception as e:
            print("Error:", e)
        time.sleep(0.5)

# Ask the user which booking to make
booking_type = input("Enter booking type (viva, cia, reep, module): ").lower()
book_slot(booking_type)
```

## Method 2: Ghost Booking (Parallel Strikes)
Use multiple devices with different networks.
Use VPN or hotspot switching for different IPs.
Open booking page and fire clicks at 8:59:59 PM sharp.
Enable auto-refresh using Chrome extensions like Super Auto Refresh Plus.
Bonus: Create a Macro recorder script (e.g., AutoHotKey or Macro Recorder).

## Method 3: Reload Storm with JavaScript
Use this JavaScript code in the browser’s developer console at 8:59:30 PM to create multiple reload attempts.
```
setInterval(() => {
   location.reload();
}, 300);

```

## Method 4: Curl/API Direct Booking
This method uses cURL for direct API requests.

```
curl -X POST https://lms2.ai.saveetha.in/api/book \
-H "Authorization: Bearer your_token" \
-d "slot_id=123&student_id=yourid"

```

## Method 5: API Sniping via DevTools
Open Chrome → DevTools (F12) → Network tab.
Click "Book" once → Observe the request.
Copy Request URL, Headers, Payload.
Reuse the payload in Postman or a script.
This makes scripting faster than using the browser.

## Method 6: Browser Automation Scripts
Selenium (Python)
```
from selenium import webdriver
from selenium.webdriver.common.by import By

options = webdriver.ChromeOptions()
options.add_argument("--headless")
driver = webdriver.Chrome(options=options)

# Login logic...
# Slot selection logic...
# Retry if failed

```

### Playwright (Recommended)
```
playwright codegen https://lms2.ai.saveetha.in/booking
```
## Method 7: DOM Sniper JavaScript
Run the following code inside the browser DevTools to keep triggering the slot booking button.
```
for i in range(1000):
    try:
        res = requests.post("https://lms2.ai.saveetha.in/api/book", data={...})
        print(res.status_code)
    except:
        pass
```
Warning: NEVER run this on real college servers. Use mock endpoints for testing.

## Method 9: Termux Mobile Sniper
```
pkg install python
pip install requests
nano sniper.py
# Paste Python script and run it
python sniper.py
```
Run this script while you're on mobile data = 100% different IP.

## Method 10: Mobile Chrome Auto-Clicking
Install an auto-clicker from Play Store:

Schedule tap at (X,Y) on the booking button.

Add 10 repetitions in a row.

Sync with 8:59:59 PM.

Set tap every 200 ms.

Optional: Pair with Chrome auto-refresh extension (Kiwi browser supports extensions).

## Method 11: Hybrid Attack Stack (Recommended)
Stack | What it does
Desktop + Wi-Fi | Selenium/Retry Script
Laptop + VPN | Browser Ghost Clicker
Phone + Hotspot | Termux Script
Friend's Phone | Manual Backup Click

This combo increases your win rate exponentially.

## Pro Tools Reference
Tool | Use
Postman | API testing and automation
Selenium | Web automation
Playwright | Headless browser scripting
Termux | Android terminal for scripts
mitmproxy | HTTP(S) traffic inspection
Charles Proxy | Deep inspection of mobile traffic
VPN (Any) | IP rotation
AutoHotKey | GUI automation in Windows
Brave/Chrome | Multiple sessions
iMacros | GUI click automation on timer
Kiwi Browser | Mobile browser with extension support


### 🔐 Final Tips
Be early: Be on the page by 8:55 PM.

Always have DevTools open.

Test your script 1 day before.

Don’t refresh the page after 9 PM (you may lose position).

Use cool heads and fast fingers.

Combine methods — automation + human timing = win.


📜 License
This toolkit is released under the MIT License.
Educational Use Only. Do NOT use on real college servers......ah bokka le chat gpt atte cheptundi nuv chey choskundam*

Sure! Here’s a modified closing tagline with a more heartfelt touch:

---

**Crafted with dedication, love, and passion by Gokul**  
💙💫🧿🤍💘
