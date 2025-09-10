Weekend Rush Table Tracker (TTV4)
ESP32-based Real-Time Table Management System for Snooker & Pool Clubs

Overview
The Weekend Rush Table Tracker (TTV4) is a comprehensive, web-based table tracking and session management system, designed specifically for billiards, snooker, and pool clubs. Powered by the ESP32 microcontroller and AsyncWebServer, it provides staff with a real-time dashboard to monitor, control, and audit all pool/snooker tables from any device on the network.

Features
Live Session Management

Start, pause, resume, and end timers for each table

Automatic real-time calculation of play time and fees

Real-Time Dashboard

Mobile-friendly web interface

Live updates (Server-Sent Events/SSE)

Input protection: no sudden data changes while staff are entering details

Session History

Complete log of all table sessions with date, staff, start & end time, duration, and charged amount

Dynamic Table Rates

Update rates at any time (even during active sessions)

Flexible per-table pricing (snooker and pool, independently managed)

Bill Splitting

One-click bill splitting for groups; instantly see per-player shares

Role-Based Structure

Demo staff and admin accounts (expandable for authentication in production)

Hardware Requirements
ESP32 Dev Board (sufficient RAM/flash for AsyncWebServer + NTP + web UI)

Optional: USB serial for debugging

Dependencies
ESPAsyncWebServer

AsyncTCP

[WiFi.h], [time.h] (Arduino Core for ESP32)

C++ Standard Library (map, vector, cmath, ctime, etc.)

Usage
Clone and Compile

Open the .ino or .cpp in Arduino IDE / PlatformIO

Adjust WiFi credentials at the top of the code

Upload to ESP32

Use standard ESP32 board upload procedure

Access the Web Dashboard

Connect to the same Wi-Fi network

Open your browser to http://<ESP32-IP-ADDRESS>

Dashboard auto-updates, no client install necessary

API Endpoints
GET /api/snapshot: JSON with live state for all tables

POST /api/{snooker|pool}/table/action: Start/Pause/End a table

POST /api/{snooker|pool}/table/rate: Update rate for a table

POST /api/{snooker|pool}/table/clear: Clear sessions for a table

POST /api/{snooker|pool}/table/split: Calculate split bill (per player)

Example Table Configurations
Snooker Table Rates: ₹4.0, ₹4.0, ₹4.5 per minute

Pool Table Rates: ₹2.0, ₹2.0, ₹2.5 per minute

