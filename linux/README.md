# Thermal Sentinel on Linux: Raspberry Pi and NVIDIA Jetson

Thermal Sentinel was built and demoed on Windows (a 2020 laptop, 32 GB RAM, Python 3.13). The code is
plain Python and the FLIR Lepton on a PureThermal board is a standard USB camera, so the same code runs on
Linux: it uses Video4Linux for the camera there instead of Windows DirectShow, chosen automatically.

Status: packaged and ready for Linux; the hackathon demo runs on Windows.

## Targets
- Raspberry Pi 4 or 5, Raspberry Pi OS 64-bit (Python 3.11)
- NVIDIA Jetson Orin Nano Super Developer Kit, JetPack 6 (Ubuntu 22.04, Python 3.10)

## Install

The source code and Linux installer are private. **Code available on request.**

## Hardware
- FLIR Lepton on a GroupGets PureThermal USB board
- Micro-USB to USB-A cable (a 6-foot cable lets the sensor sit high on a wall)
- A screen for the viewer, or run it headless later as a wall sensor that only sends alerts

## Notes
- Check the camera is seen with `v4l2-ctl --list-devices` (it shows as PureThermal).
- The voice agent needs a microphone and speaker; a USB speakerphone works well on a Pi.
- A Pi 4 handles the 9 frames per second the Lepton sends; a Jetson has room to spare.
