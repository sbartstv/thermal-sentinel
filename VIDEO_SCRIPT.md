# Thermal Sentinel GSOC: demo video script (under 2 minutes)

**Full title:** Thermal Sentinel: a privacy-first thermal SOC / GSOC security viewer with an ElevenLabs
voice agent and City of Glendale hazard data

About 270 spoken words, roughly 1 minute 50 seconds at a normal pace.

|Time|On screen|Say|
|-|-|-|
|0:00-0:10|Title card, then the app full screen|"This is Thermal Sentinel, a GSOC security viewer built for the City of Glendale. A dime-sized FLIR thermal camera, an ElevenLabs voice agent, and the city's own hazard data, on one screen."|
|0:10-0:25|Point at people outlined, head crosshairs|"It sees heat, not faces, so nobody can be identified. Every person in view gets an outline and a temperature on their head, even people across the room. It counts who's in view and who has entered."|
|0:25-0:35|Click through 3 or 4 palettes|"Eight thermal color palettes: Ironbow, White Hot, Black Hot, Rainbow, Hot Metal, Inferno, Arctic and Jet."|
|0:35-0:50|Walk into view; agent speaks; phone buzzes|"When someone walks in at night, the ElevenLabs agent speaks up. The alert also hits my phone with the thermal snapshot, by email, and by text."|
|0:50-1:05|Phone: tap Answer, agent talks|"Tap Answer and the same agent talks to me on my phone, already briefed. No phone company, no monthly fee."|
|1:05-1:15|Lighter over the spot square; FIRE ALERT|"A lighter: fire alert. A hot laptop that was already there doesn't trigger it. Only new heat does."|
|1:15-1:30|Press V, ask "nearest fire station?" and "news in Glendale?"|"The agent has live tools. It knows the count, the temperatures, the city's hazard zones, the nearest fire station, police and hospital, and today's Glendale news."|
|1:30-1:40|City panel, zoom the map, open the dashboard on a phone|"Live weather, earthquakes and wildfires, a map of every responder, and a web dashboard anyone on the team can open."|
|1:40-1:55|Back to full screen|"For the city, residents and small businesses, it lowers liability: no faces recorded, a timestamped evidence log, and fewer false 911 calls. Thermal Sentinel. Built today at Jewel City Hacks 6.0."|

## Features

* People detection and counting by body heat, near or far (Range: NEAR, MID, FAR)
* Segmentation: an outline around each person, split apart even when people overlap
* Temperature pinpoint on each person's head, in Fahrenheit and Celsius
* Fire alert from a spot meter (122 F) and an area alarm (140 F), ignoring heat that was already there
* ElevenLabs voice agent at the desk, speaking alerts built from what the sensor saw
* Agent live tools: people count, temperatures, recent events, city data, news, open a story,
mark a false alarm, switch the system on or off, email the log
* ElevenLabs agent on the phone: alert notification with snapshot and an Answer button
* Alerts by phone push, email with screenshot, and text message
* Activity log with a timestamp and snapshot for every event, emailed on demand, hourly or daily
* Night schedule: system on at 6 PM, off at 7 AM
* System ON/OFF switch, voice alerts on/off, movement lines on/off
* City of Glendale hazard zones for the site: wildfire, FEMA flood, fault, liquefaction, landslide,
dam inundation, debris flow
* Nearest fire station, police station and hospital
* Live National Weather Service alerts, USGS earthquakes, nearby wildfires
* Glendale news headlines, clickable, read aloud by the agent
* Zoomable Glendale map with fire stations, police, hospitals, City Hall, libraries and schools
* Camera health: the sensor's own internal temperature, with warnings
* Web dashboard, live from anywhere
* One-click Desktop launcher; recorded demo fallback if the camera is unplugged

## Thermal color palettes

Ironbow, White Hot, Black Hot, Rainbow, Hot Metal, Inferno, Arctic, Jet

## Tools and tech

* **Hardware:** FLIR Lepton thermal sensor, PureThermal USB board, Windows laptop
* **Vision:** Python, OpenCV, NumPy (body-heat segmentation, watershed, tracking)
* **Voice:** ElevenLabs Agents, ElevenLabs Python SDK, client tools, dynamic variables
* **City data:** Glendale GIS MCP (Jewel City Hacks), City of Glendale ArcGIS, CAL FIRE, FEMA, CGS, DWR, USGS
* **Live feeds:** National Weather Service, USGS Earthquakes, NIFC wildfires, Google News, Esri basemap
* **Alerts:** ntfy push, Gmail SMTP email, carrier email-to-text
* **Dashboard:** v0 by Vercel, Next.js, Vercel hosting
* **Code:** GitHub

## Contests to enter

* **Main challenge (City of Glendale):** help residents understand the emergency risks where they live
and how to prepare, using the city's hazard and responder data
* **ElevenLabs Champion:** two ElevenLabs agents, one at the desk with live tools, one on the phone
* **Best Hardware Hack:** FLIR Lepton thermal camera with on-screen sensor health
* **LOSF extra credit (startup):** helps residents and businesses while lowering liability and burden
on the city: privacy by design, evidence log, fewer false 911 calls, early fire warning

## Links

* Dashboard: https://thermal-sentinel-black.vercel.app
* Code: https://github.com/sbartstv/thermal-sentinel

