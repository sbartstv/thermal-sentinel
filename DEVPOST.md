# Devpost submission: Thermal Sentinel GSOC

Copy each part into the matching Devpost box.

---

## PROJECT NAME
Thermal Sentinel GSOC

## ELEVATOR PITCH (short tagline, under 200 characters)
A privacy-first thermal security center: a FLIR sensor counts people and catches fires, an ElevenLabs AI agent talks you through it, and Glendale's city data sits beside the live view.

---

## ABOUT THE PROJECT (the big text box; paste everything from here to "END OF ABOUT")

**Jewel City Hacks 6.0 · City of Glendale · "Think Globally, Build Locally"**

### Prizes we're entering
- **Best Software Hack**
- **Best Hardware Hack**
- **Grand Champion**
- **ElevenLabs Champion**
- **LOSF extra credit** (startup: helps residents and businesses while lowering liability and burden on the city)
- **Built with Vercel:** the live web dashboard was built with v0 and is hosted on Vercel

### Inspiration
City Hall, libraries, schools and small shops can't put a guard in every hallway, and ordinary cameras record faces, which brings privacy and liability problems. A thermal sensor sees heat, not identity. We wanted a security operations center (SOC / GSOC) that fits on a laptop, respects privacy, and can talk to you about what it sees, while also helping people understand the emergency risks at their own address.

### What it does
- **Counts people by body heat.** "In view" shows who's there now, "Entered" counts everyone who has walked in. Each person gets a green outline (segmentation) and a crosshair with the temperature on their head. Range NEAR / MID / FAR picks whether it watches only the person at the desk, a room, or everyone in view.
- **Catches fires.** A spot meter (122 F) and an area alarm (140 F) raise a heat alert. Heat that was already in the room, like a laptop vent, is learned and ignored; only new heat alarms.
- **ElevenLabs is the GSOC AI agent.** It runs as two agents: a **desk agent** that speaks out loud through the computer and a **phone agent** you reach from any alert. It announces fire and heat alerts and who walks into the room, then answers live questions: how many people are in view, the temperatures, what happened earlier, the city's hazard zones, the nearest fire station, police and hospital, weather, earthquakes and wildfires. It reads the Glendale news aloud, opens a story on screen when asked, and can mark a false alarm, switch the system on or off, and email the log.
- **Free phone alerts with the ElevenLabs voice.** Each alert reaches your phone as a push notification in the ntfy app, with the thermal snapshot. Its Answer button opens the ElevenLabs agent right on the phone, already briefed, so you talk to the agent without needing a phone call or a phone number. Alerts also go by email with the screenshot, with a text-message option.
- **Knows Glendale.** For the site's address it shows the City of Glendale's hazard zones (wildfire, FEMA flood, fault, liquefaction, landslide, dam inundation, debris flow), the nearest first responders, live weather alerts, earthquakes, wildfires and Glendale news.
- **Map.** Built from the City of Glendale's own GIS and the organizers' Glendale GIS MCP, on Esri ArcGIS street and satellite maps, with fire stations, police, hospitals, City Hall, libraries and schools marked. Instant zoom and Google Street View in one click.
- **Live web dashboard** on Vercel: the sensor's readings and every alert with its snapshot, from anywhere.
- **Run it like a SOC:** system on/off, a 6 PM to 7 AM night schedule, eight thermal palettes, movement lines, an event log with a timestamp and snapshot for every event (emailed now, hourly or daily), and the camera's own internal temperature on screen.

### How we built it
- **Hardware:** a FLIR Lepton thermal sensor on a GroupGets PureThermal USB board, a 6-foot micro-USB to USB-A cable, and a 2020 Razer laptop with 32 GB RAM on Windows 11. The sensor is read as raw radiometric frames, so every pixel is a real temperature.
- **Software:** Python 3.13, coded with Claude as my AI coding assistant. OpenCV and NumPy do the vision: body-heat segmentation, splitting people who overlap by finding each head's warm peak, and tracking them frame to frame.
- **Voice:** ElevenLabs Agents. The desk agent runs through the ElevenLabs Python SDK with live tools wired into the app; the phone agent opens from a link that carries the alert's facts.
- **City data:** the Glendale GIS MCP from the Jewel City Hacks organizers (run locally on the laptop), the City of Glendale's ArcGIS services, Esri ArcGIS maps, and public feeds from the National Weather Service, USGS, NIFC and Google News.
- **Alerts:** the ntfy app for phone push notifications, Gmail for email.
- **Dashboard:** v0 by Vercel, hosted on Vercel.
- **Portable:** built on Windows; the same code is packaged for Linux on a Raspberry Pi or NVIDIA Jetson Orin Nano Super, since the sensor is plug-and-play USB.

### Challenges we ran into
- **Phone calls vs. time and cost.** The ElevenLabs agent is connected to a Twilio caller ID and the code places real calls, but a Twilio trial won't dial out. Due to time constraints and cost, we decided to use ntfy for free phone alerts and route the ElevenLabs voice agent through ntfy instead of buying a Twilio number. For about $20, Twilio would add real phone-call alerts on top.
- **A crowded room.** People sitting behind me kept merging into one shape or being missed. We moved from background subtraction to body-heat segmentation, then split merged shapes by each person's warm peak.
- **Counting entries.** Early versions reused a person's number when someone new walked in. We tuned tracking so every walk-in adds to the count.
- **False fire alarms.** A hot laptop looked like a fire, so alerts now need new heat that lasts several frames.
- **A noisy hackathon room** kept interrupting the agent mid-sentence, so we made it finish what it's saying and gave it a calmer voice.

### Accomplishments that we're proud of
- A working thermal SOC built in one day by one person, with a real sensor and real alerts.
- An AI agent that talks about what the sensor sees right now and reads the city's own hazard data for the address.
- Alerts that reach a phone with a picture and a voice conversation, at zero cost.
- Privacy by design: nothing in the system can identify a person.

### What we learned
- At 160 by 120 pixels, simple physics-based rules on real temperatures work well for people and fire.
- Voice agents become far more useful with live tools than with a script.
- Public city GIS data becomes approachable when you can just ask about it.

### What's next for Thermal Sentinel GSOC
- A wall-mounted box on a Raspberry Pi or Jetson, with many sensors feeding one dashboard across city buildings.
- Real phone-call alerts through a paid Twilio number, and escalation when an alert isn't answered.
- Doorway in/out counting, loitering and person-down detection.
- A resident mode: say your address, hear your hazards and how to prepare.

### How it lowers liability and burden on the city (LOSF)
- No faces recorded: no privacy claims and no identifiable footage to leak or subpoena.
- A timestamped log with snapshots documents what happened and when.
- The guard checks with the agent first, cutting false 911 calls; the agent never claims to dispatch anyone and says to call 911 for a real emergency.
- Early fire warning limits losses for businesses and residents.

END OF ABOUT

---

## BUILT WITH (Devpost tag box: type each one and press Enter)
python, opencv, numpy, flir-lepton, purethermal, groupgets, elevenlabs, elevenlabs-agents, vercel, v0, nextjs, ntfy, gmail, arcgis, esri, glendale-gis-mcp, mcp, national-weather-service, usgs, github, claude, windows, linux, raspberry-pi, nvidia-jetson

## TRY IT OUT LINKS
- https://github.com/sbartstv/thermal-sentinel
- https://thermal-sentinel-black.vercel.app

## IMAGE GALLERY (upload in this order, from the "Devpost screenshots" folder on the Desktop)
1. full screen
2. fire alert
3. people with head temperatures
4. city data, map and news
5. rainbow palette

## VIDEO
Upload the demo video to YouTube (unlisted is fine) and paste its link.

## OTHER QUESTIONS DEVPOST MAY ASK
- **Team members:** add any teammates by their Devpost usernames.
- **Which prizes / challenges:** tick Best Software Hack, Best Hardware Hack, Grand Champion, ElevenLabs Champion and the LOSF extra credit, plus any Vercel option listed.
