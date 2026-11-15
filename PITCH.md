# Thermal Sentinel: pitch and demo order

## One line
A dime-sized thermal camera and an ElevenLabs voice agent that watch a space when nobody else can,
tell you what's happening, and know the City of Glendale's hazard and responder data for that address.

## The problem (30 seconds)
- City buildings, libraries, schools and small shops can't staff a guard at every hallway all night.
- Regular cameras record faces, which creates privacy and liability problems, especially in schools.
- When something does happen, people don't know the risks at their own address or who responds.

## What it does (45 seconds)
- **Sees heat, not faces.** Counts people, outlines each one, reads temperature at each head. Nobody can be identified.
- **Fire alert** when something new gets hot. Heat that was already in the room (a laptop, a heater) is ignored.
- **Talks.** An ElevenLabs agent speaks the alert and answers questions: how many people, how hot, what happened earlier.
- **Knows Glendale.** For the site's address it pulls the city's GIS data: wildfire, flood, fault and dam hazard zones,
  and the nearest fire station, police station and hospital. Plus live weather alerts, earthquakes, wildfires and local news.
- **Reaches you anywhere, free.** Phone alert with the thermal snapshot and an Answer button that opens the agent on
  your phone. Email with the screenshot. Text message. No phone company, no monthly fee.
- **Runs on anything.** Today a laptop; the same software fits a Raspberry Pi on a wall.

## Who it's for
1. **City of Glendale (SOC / GSOC):** City Hall, libraries, the fire department, the police real-time center. One screen, many sensors.
2. **Residents (the main challenge):** "What are the emergency risks where I live, and what do I do?" Ask the agent. It answers from
   the city's own hazard maps for your address and tells you who your nearest responders are.
3. **Businesses and residents (LOSF, lower liability and burden on the city):**
   - No faces recorded means no privacy claims and no footage to subpoena or leak.
   - A timestamped log with snapshots is evidence of what happened and when.
   - Early fire warning cuts losses and cuts 911 calls for false alarms: the guard checks the agent first.
   - The agent never claims to dispatch anyone and says to call 911 for a real emergency.

## Demo order (2 minutes)
1. Screen up, **SYSTEM ON**, range **FAR**. Point at the outlines and head temperatures on people in the room.
2. Step out of view and walk back in. The count goes up; the phone buzzes with the snapshot.
3. Tap **Answer** on the phone. The agent explains the alert. Ask: "Where's the nearest fire station?"
4. Press **V** at the desk. Ask: "How many people are in the room?" then "What's the news in Glendale?"
5. Hold a lighter or hot cup over the spot square. **FIRE ALERT** flashes, the map marker turns red.
6. Show the city data panel: hazard zones, responders, live feeds. Click a link.
7. Open the web dashboard link: same alerts, visible from anywhere.

## Prizes to name out loud
- **ElevenLabs Champion:** two agents (desk with live tools, phone with the alert briefing), built on ElevenLabs Agents.
- **Best Hardware Hack:** FLIR Lepton thermal sensor, with its own temperature monitored on screen.
- **Main challenge:** residents understand risks where they live, from Glendale's GIS data through the organizers' MCP package.
- **LOSF extra credit:** privacy by design, evidence log, fewer false 911 calls, liability guardrails in the agent.

## If something breaks
- Camera blank: unplug and replug the USB. The app reconnects by itself.
- Camera dead: Desktop icon **Thermal Sentinel Viewer (replay backup)** runs a recording.
- Agent won't stop talking: press **V** to hang up.
- Too noisy for the desk agent: use the phone Answer button instead.

## After the hackathon
- Cancel ElevenLabs Creator before December 14.
- Reset the Twilio auth token and delete the Gmail app password (both were typed into chat).
