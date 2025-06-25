# Remote Cam

Modern web interface to view FLV camera streams from 3D printers over LAN.

## ✨ Features

- 🎥 Live FLV video playback via `flv.js`
- 📡 Custom configuration of protocol, IP and port
- 📊 Visual indicators for status, speed and latency
- 🛠️ Manual controls for playback, reconnect and log clearing
- 📋 Real-time log with severity levels
- 📱 Responsive design for desktop and mobile

## ⚙️ Technologies Used

- HTML5 + CSS3 (responsive and themed UI)
- Vanilla JavaScript (no heavy frameworks)
- External library: `flv.js` via CDN
- Uses `localStorage` to save user config

## 🚀 How to Use

1. Enable **LAN mode** on your 3D printer (e.g., Anycubic Kobra S1)
2. Copy this repository to your local machine or server
3. Open the file `anycubic-s1-cam-v3.html` in a modern browser
4. Enter the printer’s IP address/domain and FLV port (e.g., `192.168.1.6:18088/flv`)
5. Click **Connect** to start streaming

## 📦 Files

- `anycubic-s1-cam-v3.html` → Main interface with embedded HTML, CSS, and JS
- No backend server or extra dependencies required

## 🧪 Compatibility

- 📱 Compatible with iPad (Safari/Chrome), Android (Chrome/Edge), and PC (Chrome/Firefox/Edge); currently not working on iPhone due to FLV limitations

Tested with:
- ✅ Anycubic Kobra S1
- ✅ Modern browsers with JavaScript support
- ⚠️ Should work with any printer that streams FLV over LAN

## ❗ Disclaimer

> This project is an open-source tool and is **not affiliated with or endorsed by Anycubic** or any other manufacturer.  
> “Anycubic” and “Kobra S1” are trademarks of their respective owners.  
> This software is intended for personal and educational use only.

## 🛡️ License


This project is licensed under the Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0).

You are free to:
- Use, copy, and modify the code for personal and non-commercial purposes.

You may not:
- Use this project or any part of it for commercial purposes.
- Sell, license, or monetize this software or its derivatives.

[Read full license](https://creativecommons.org/licenses/by-nc/4.0/)

---

Developed by Teo.  
Open source project with no heavy external dependencies.
