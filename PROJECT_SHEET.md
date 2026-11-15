# Thermal Sentinel GSOC: project sheet

**Thermal Sentinel: a privacy-first thermal SOC / GSOC security viewer with an ElevenLabs voice agent
and City of Glendale hazard data.** Jewel City Hacks 6.0, City of Glendale, November 14, 2026.

- Live dashboard: https://thermal-sentinel-black.vercel.app
- Code (Windows and Linux): https://github.com/sbartstv/thermal-sentinel

## Contests we're entering

1. **Best Software Hack:** a Python app with body-heat segmentation and tracking, two ElevenLabs voice
   agents, live City of Glendale data, maps, alerts and a web dashboard.
2. **Best Hardware Hack:** a FLIR Lepton thermal sensor on a GroupGets PureThermal USB board, read as raw
   temperatures, with the sensor's own health on screen; plug-and-play on Windows, Raspberry Pi and Jetson.
3. **Grand Champion:** a local municipal challenge, residents' emergency risk and after-hours building
   safety, built to scale from one laptop to sensors across city buildings.
4. **ElevenLabs Champion:** a desk agent that speaks every alert and answers with seven live tools, and a
   phone agent that opens from an alert, already briefed.
5. **LOSF extra credit (startup):** helps residents and businesses while lowering liability and burden on
   the city: no faces recorded, a timestamped evidence log, early fire warning, fewer false 911 calls.
6. **Top 5 Hackathon Hackers:** individual award for communication, professionalism and leadership.

## Built on, and where it runs

- **Built and demoed on:** a 2020 Razer laptop, 32 GB RAM, Windows 11, Python 3.13.
- **Runs anywhere Python runs:** the sensor is plug-and-play USB, so the same code runs on Linux. The
  `linux` folder installs it on a **Raspberry Pi** or an **NVIDIA Jetson Orin Nano Super Developer Kit**
  for a small box mounted on a wall. (The Linux version is packaged and ready; the demo runs on Windows.)

### Hardware
- **FLIR Lepton** longwave thermal sensor (160 x 120 radiometric: every pixel is a temperature)
- **GroupGets PureThermal** USB board (shows up as a standard USB camera)
- **6-foot micro-USB to USB-A cable**, so the sensor can sit high on a wall or a monitor edge
- Same hardware plugs straight into a Raspberry Pi or NVIDIA Jetson

## Features

### People detection
- Counts people by body heat: **In view** now and **Entered** in total
- **Range:** NEAR (only the person at the desk), MID (a normal room), FAR (everyone, default)
- **Segmentation:** an outline around each person, split apart even when people overlap
- **Temperature pinpoint** on each person's head, in Fahrenheit and Celsius
- Movement lines showing where each person walked (on/off)
- Sees heat, not faces: nobody can be identified

### Fire detection
- Spot meter fire alert at 122 F / 50 C, area heat alarm at 140 F / 60 C, both adjustable
- Ignores heat that was already there (laptop vents, heaters); only new heat alarms
- Fire alerts always get through, and the agent opens with "Heat alert"

### ElevenLabs voice agent
- Speaks each alert at the desk in a sentence built from what the sensor saw
- Talk to it anytime (V); voice alerts on/off
- Live tools: people count, temperatures, recent events, city data, news, open a news story,
  mark a false alarm, switch the system on or off, email the log
- Phone agent: alert notification with an Answer button that opens the agent on the phone, free
- Real phone calls are wired up (Twilio caller ID connected to ElevenLabs); switched off for the demo
  because a Twilio trial won't dial out and a paid number wasn't worth buying for a hackathon

### Alerts
- Phone push notification with the thermal snapshot
- Email with the screenshot ("Screenshot to"), text message ("Text to")
- Activity log emailed now, hourly or daily ("Logs to"); an empty box sends nothing

### City of Glendale data (for the site's address)
- Hazard zones: wildfire (CAL FIRE), FEMA flood, fault rupture, liquefaction, landslide,
  dam inundation, debris flow
- Nearest fire station, police station and hospital
- Live National Weather Service alerts, USGS earthquakes, nearby wildfires (NIFC)
- Glendale news headlines, clickable and read aloud by the agent
- Esri ArcGIS color street map and satellite view, instant zoom, with fire stations, police, hospitals,
  City Hall, libraries and schools marked; Google Street View in one click

### System
- SYSTEM ON/OFF (fire detection always stays on), night schedule (6 PM to 7 AM)
- Eight thermal palettes: Ironbow, White Hot, Black Hot, Rainbow, Hot Metal, Inferno, Arctic, Jet
- Camera health: the sensor's own internal temperature, green/amber/red
- Activity log with a timestamp and snapshot for every event
- Live web dashboard from anywhere
- One-click launcher; if the camera is unplugged, press P to run a recorded demo

## Tools and tech
- **Language:** Python (3.10 or newer; built on 3.13)
- **Vision:** OpenCV, NumPy: body-heat segmentation, watershed splitting, tracking
- **Voice:** ElevenLabs Agents, ElevenLabs Python SDK, client tools, dynamic variables
- **City data:** Glendale GIS MCP (Jewel City Hacks), City of Glendale ArcGIS, CAL FIRE, FEMA,
  California Geological Survey, DWR, USGS
- **Maps and feeds:** Esri ArcGIS basemaps, National Weather Service, USGS Earthquakes, NIFC, Google News
- **Alerts:** ntfy push, Gmail email, carrier email-to-text; Twilio ready for calls
- **Dashboard:** v0 by Vercel, Next.js, Vercel hosting
- **Platforms:** Windows 11 (built and demoed), Linux: Raspberry Pi OS, NVIDIA JetPack (packaged)
- **Code:** GitHub
