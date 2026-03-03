# Smart-Waste-Management-System
Smart Waste Management System built using Node-RED and Twilio SMS API to monitor waste bin levels in real-time. The system validates input, visualizes data using dashboard gauges and charts, and automatically sends SMS alerts when the bin reaches a threshold, improving efficiency and preventing overflow.
Project Overview

The Smart Waste Management System is an IoT-based monitoring solution developed using Node-RED Dashboard and Twilio SMS API.

This system:

Accepts bin level input (0–100%)

Displays real-time gauge & chart

Sends SMS alerts when the bin is full (≥75%)

Sends normal status SMS when below threshold

Your uploaded Node-RED flow file:
📂 flows.json 

flows

🛠️ System Architecture
1️⃣ Node-RED Dashboard
4

Used For:

Creating flow logic

Designing dashboard UI

Handling threshold validation

Connecting Twilio SMS API

2️⃣ Twilio SMS Integration
4

Used For:

Sending SMS when bin ≥ 75%

Sending normal status SMS

Alerting municipal authority / user

💻 How to Download & Install Node-RED
Step 1: Install Node.js

Download from: https://nodejs.org

Install LTS version

Verify installation:

node -v
npm -v
Step 2: Install Node-RED

Open Command Prompt:

npm install -g --unsafe-perm node-red

Start Node-RED:

node-red

Open in browser:

http://localhost:1880
📦 Install Required Nodes

Open Node-RED → Menu → Manage Palette → Install:

Install:

node-red-dashboard

node-red-node-twilio

Or use command:

cd ~/.node-red
npm install node-red-dashboard
npm install node-red-node-twilio

Restart Node-RED.

📂 How to Import Your Project Flow

Open Node-RED

Click ☰ Menu → Import

Select your file:

flows.json

Click Import

Click Deploy

Your dashboard will appear at:

http://localhost:1880/ui
📱 How to Create Twilio Account

Go to https://www.twilio.com

Sign up (Free trial available)

After login, go to Console Dashboard

Copy:

Account SID

Auth Token

Buy / Get a Twilio phone number

🔑 How to Configure Twilio in Node-RED

In your flow file 

flows

 the Twilio node is already present.

To configure:

Double-click Twilio Out Node

Click ✏️ edit next to Twilio configuration

Enter:

Account SID

Auth Token

Twilio Phone Number (From Number)

Click Add → Done → Deploy

📊 Flow Logic Explanation

Your Flow Contains:

🔹 1. Bin Level Input (UI Text Input)

User enters value (0–100)

🔹 2. Validate Function

Checks:

If not number → error

If <0 or >100 → invalid

Else → pass to next node

🔹 3. Switch Node (Threshold Check)

Condition:

If ≥ 75 → Bin Full

If < 75 → Bin OK

🔹 4. Twilio SMS Nodes

Bin Full SMS

Bin OK SMS

🔹 5. Dashboard Components

Gauge (Live percentage)

Chart (Time-based graph)

Debug node (Error display)

📨 How SMS Works

If bin level ≥ 75:

Alert: Waste bin is full. Immediate action required!

If bin level < 75:

Bin status normal.

You can customize message inside Twilio node:

Set msg.payload before Twilio node using Function node.

📂 Project Folder Structure (GitHub)
smart-waste-management/
│
├── flows.json
├── README.md
├── screenshots/
│   ├── dashboard.png
│   ├── flow.png
│
└── package.json (optional)
🚀 How to Run the Project

Install Node.js

Install Node-RED

Install dashboard & twilio nodes

Import flows.json

Configure Twilio credentials

Deploy

Open:

http://localhost:1880/ui
