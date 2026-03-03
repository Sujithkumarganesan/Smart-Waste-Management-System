# ♻️ Smart Waste Management System  
### IoT-Based Waste Monitoring using Node-RED & Twilio SMS  

---

## 📌 Project Overview

The **Smart Waste Management System** is an IoT-based monitoring solution developed using **Node-RED Dashboard** and **Twilio SMS API**.

This system:

- Accepts bin level input (0–100%)
- Displays real-time gauge and chart
- Sends SMS alerts when bin level ≥ 75%
- Sends normal status SMS when below threshold

Flow file included in this repository:  
📂 `flows.json`

---

## 🏗️ System Architecture

### 1️⃣ Node-RED Dashboard

Used for:

- Creating flow logic  
- Designing dashboard UI  
- Handling threshold validation  
- Connecting Twilio SMS API  

### 2️⃣ Twilio SMS Integration

Used for:

- Sending SMS when bin ≥ 75%  
- Sending normal status SMS  
- Alerting user or municipal authority  

---

## 💻 Installation Guide

### Step 1: Install Node.js

1. Download from: https://nodejs.org  
2. Install LTS version  
3. Verify installation:

```bash
node -v
npm -v
```

---

### Step 2: Install Node-RED

Open Command Prompt and run:

```bash
npm install -g --unsafe-perm node-red
```

Start Node-RED:

```bash
node-red
```

Open in browser:

```
http://localhost:1880
```

---

## 📦 Install Required Nodes

In Node-RED:

Menu → Manage Palette → Install  

Install:

- node-red-dashboard  
- node-red-node-twilio  

Or use terminal:

```bash
cd ~/.node-red
npm install node-red-dashboard
npm install node-red-node-twilio
```

Restart Node-RED after installation.

---

## 📂 Import Project Flow

1. Open Node-RED  
2. Click ☰ Menu → Import  
3. Select `flows.json`  
4. Click **Import**  
5. Click **Deploy**

Dashboard will be available at:

```
http://localhost:1880/ui
```

---

## 📱 Twilio Account Setup

1. Go to https://www.twilio.com  
2. Create an account  
3. Open Console Dashboard  
4. Copy:
   - Account SID  
   - Auth Token  
5. Get a Twilio phone number  

---

## 🔑 Configure Twilio in Node-RED

1. Double-click **Twilio Out Node**  
2. Click edit (✏️) next to configuration  
3. Enter:
   - Account SID  
   - Auth Token  
   - Twilio Phone Number  
4. Click **Add → Done → Deploy**

---

## 🔄 Flow Logic Explanation

### 1️⃣ Bin Level Input
User enters value between 0–100.

### 2️⃣ Validation Function
- Rejects non-numeric values  
- Rejects values < 0 or > 100  
- Passes valid input forward  

### 3️⃣ Threshold Check (Switch Node)

- ≥ 75 → Bin Full  
- < 75 → Bin OK  

### 4️⃣ SMS Notification

- "Bin Full" SMS sent when threshold exceeded  
- "Bin OK" SMS sent when below threshold  

### 5️⃣ Dashboard Output

- Live Gauge (percentage view)  
- Real-time Chart  
- Debug messages for errors  

---

## 📨 SMS Alert Messages

If bin level ≥ 75:

```
Alert: Waste bin is full. Immediate action required!
```

If bin level < 75:

```
Bin status normal.
```

Messages can be customized using a Function node before the Twilio node.

---

## 📁 Project Structure

```
smart-waste-management/
│
├── flows.json
├── README.md
├── screenshots/
│   ├── dashboard.png
│   ├── flow.png
│
└── package.json (optional)
```

---

## 🚀 How to Run the Project

1. Install Node.js  
2. Install Node-RED  
3. Install required nodes  
4. Import `flows.json`  
5. Configure Twilio credentials  
6. Deploy  
7. Open:

```
http://localhost:1880/ui
```

---

## ✨ Features

- Real-time waste level monitoring  
- Automatic SMS alerts  
- Threshold-based automation  
- Dashboard visualization  
- Input validation  
- Easy IoT integration  

---

## 🔮 Future Enhancements

- ESP8266 / ESP32 sensor integration  
- Ultrasonic sensor automation  
- Cloud database integration  
- GPS tracking  
- AI-based waste prediction  
- Mobile app integration  

---

## 📜 License

This project is developed for educational and research purposes.
