# Remote Cam

Modern web interface to view FLV camera streams from 3D printers over LAN.

## ✨ Features

- 🎥 Live FLV video playback via `flv.js`
![image](https://github.com/user-attachments/assets/e731c66d-a1e0-480c-8e83-2d8834c89398)


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
3. Open the file `Remote-cam.html` in a browser
4. Enter the printer’s IP address/domain and FLV port (e.g., `192.168.1.6:18088/flv`)
5. Click **Connect** to start streaming

## 📦 Deployment Options

This project can be easily deployed in multiple environments:

- 🐳 **Docker / Proxmox LXC**: You can host the interface from a container (LXC or Docker) inside Proxmox. Just place the HTML file in a shared or mounted volume and serve it via a lightweight HTTP server (see below).
- 🌐 **Domain with Nginx Proxy Manager**: You can point a custom domain to the server where this is hosted using [Nginx Proxy Manager](https://nginxproxymanager.com/). Ensure:
  - The printer's stream is accessible at `http://192.168.1.6:18088`
  - The interface is served from `http://192.168.1.9:8080`
- 🏠 **Home Assistant**: You can embed the interface into your Home Assistant dashboard using the **Web Page card**. Just provide the full local or external URL where the interface is hosted.

## ⚙️ Local Deployment

To deploy the interface manually on any machine:

1. Place `Remote-cam.html` in any directory.
2. From that directory, run a simple HTTP server:

   ```bash
   python3 -m http.server 8000
   ```

3. Open your browser and go to `http://<your-machine-ip>:8000/Remote-cam.html`

This method works great on local networks, lightweight VMs, or containers.

### ⏱️ Persistent Hosting

To keep the interface running permanently without needing to run the command manually every time, you can:

- Use a systemd service (Linux):
  
  ```bash
  [Unit]
  Description=Remote Cam Web Server
  After=network.target

  [Service]
  WorkingDirectory=/path/to/your/html
  ExecStart=/usr/bin/python3 -m http.server 8000
  Restart=always

  [Install]
  WantedBy=multi-user.target
  ```

  Save this as `/etc/systemd/system/remotecam.service`, then run:

  ```bash
  sudo systemctl daemon-reexec
  sudo systemctl enable remotecam
  sudo systemctl start remotecam
  ```

- Or use `pm2` (cross-platform):

  ```bash
  npm install -g pm2
  pm2 start "python3 -m http.server 8000" --name remote-cam
  pm2 save
  pm2 startup
  ```

## 📦 Files

- Main interface with embedded HTML, CSS, and JS
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
