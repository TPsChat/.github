# Chat Application

## System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                         Chat Application                        │
└─────────────────────────────────────────────────────────────────┘

┌──────────────┐      REST API (/api/*)     ┌──────────────┐
│   Android    │ ─────────────────────────▶ │              │
│   Client     │                            │              │
│              │ ◀───────────────────────── │              │
└──────────────┘      WebSocket/Socket.IO   │   Node.js    │
                                            │   Server     │
                                            │  (Express)   │ 
┌──────────────┐      REST API (/api/*)     │              │    
│   WebAdmin   │ ─────────────────────────▶ │              │ 
│   (React)    │ ◀───────────────────────── │              │ 
└──────────────┘      (Polling every 30s)   └──────┬───────┘
                                                   │
                                                   ▼
                                            ┌──────────────┐
                                            │   MongoDB    │
                                            │  Database    │
                                            └──────────────┘
---

## Overview

Full-stack chat system including:

* Node.js Server
* React Web Admin
* Android Client

---

## Quick Start

### Requirements

* Node.js (v16+)
* MongoDB
* Android Studio

---

### Run Server

```bash
cd ServerNodeJS/Server
npm install
cp .env.example .env
npm run dev
```

---

### Run WebAdmin

```bash
cd WebAdmin
npm install
cp .env.example .env
npm run dev
```

---

### Run Android Client

* Open `Client` in Android Studio
* Set `SERVER_IP`
* Run app

---

## Configuration

Set server IP in:

* `ServerNodeJS/Server/.env`
* `WebAdmin/.env`
* `Client/.../ServerConfig.java`

---

## Testing

* Server: `/api/server/health`
* WebAdmin: `http://localhost:5173`
* Client: login/register

---

## Common Issues

* MongoDB not running
* Wrong IP / port
* Firewall blocking
* Emulator uses `10.0.2.2`

---

## Documentation

* Server: https://github.com/TPsChat/NodejsServer/tree/main/Server/README.md
* WebAdmin: https://github.com/TPsChat/WebAdmin/tree/main/README.md
* Client: https://github.com/TPsChat/AndroidApp/tree/main/README.md

---

## Project Structure

```
ServerNodeJS/Server
WebAdmin
Client
```

---

## Notes

* All components must use same server IP
* Optional services can be added later

---
