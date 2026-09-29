---
title: 2026-09-17 infra-interest minutes
description: 
published: true
date: 2026-09-18T03:18:57.618Z
tags: minutes, infra-interest
editor: markdown
dateCreated: 2026-09-18T03:18:57.618Z
---

# infra-interest agenda 2026-09-17


Collaborative meeting minutes:  https://pad.disroot.org/p/pp-infra-interest 
Please help us take notes by joining this document from your laptop.

- Meeting topics: Homelab Monitoring  

# Attendance
  
  * Host: Rechner
  * In-person: Geo, Scout, Parsec, Kinn, Howz
  * Online:

# Introductions. 
Name, background, goals or interests for the meeting.
  - Rechner (he/him): CTO @ Pawprint, Infra-wrangler in default life, helping people homelab
  - Geo: Troubleshooting web serial this whole time, works in offensive security at big corp, homelabbing for a long time with servers under his bed.
  - Kinn: kina IT cybersecurity, managed networks and ran cyber club in uni, server rack in room he can somehow sleep through.
  - Parsec: SWE, also with a terrarium with a gecko! named Erf, with stats he wants to stream.
  - Howz: lab technician working in startups, looking for a new thing.  Likes to develop air quality monitor (raspi sandwich).
  - Scout (he/him): Student, defacto sysadmin at the uni: endpoints to servers to whatever the researchers want at the moment, small homelab of NUCs and a NAS, recently moved into evocative's SJC datacenter with a small setup.

# Lesson or demo

## Homelab monitoring

- Pawprint uses Beszel to monitor it's VMs and containers. Oriented for container monitoring and easy to deploy with Docker or as a systemd service.
- Monitors everything from CPU, GPU, disk usage, RAM usage, temperature readings, etc. Can also view S.M.A.R.T. readings if using real disks.
- You can configure alerts on Beszel to respond to events fed by the monitor. Can do email, telegram, Shoutrr (signal, slack, teams, lots of things). Can be scoped for individual containers or globally.
- Can run Beszel as an agent somewhere off-premise, uses SSH for communication among things.

- Uptime Kuma, a node.js application which can do a lot of monitoring. Can do TCP, ICMP, and more. Works with various databasing software.
- Has various methods of notifications much like Beszel.
- Can also do TLS certificate monitoring.
- Can do grouping and labels of services and monitors. For alerts, you can set buffers so that you don't get alerts immediately when a service doesn't respond (useful for smaller intermittent outages).

- LibreNMS, made specifically as a network monitoring system. Uses SNMP for it's monitoring. 
- Has an SNMP agent which goes around and asks for information from devices on the network. 
- Has visibility through its "Neighbors" tab, showing what ports are plugged into what devices adjacent to each other.
- Has integration with Oxidize, which can grab configurations and store it in Git for you.
- Has a whole bunch of other miscellaneous monitoring tools for SMART, Fan speeds, and more.

- Netbox, an inventory management service thing which people use a network monitor. Can describe where things are plugged in, the layout of the network. Can literally describe the layout of an entire rack (very cool).
- A plugin exists called "Diode" which feeds from SNMP and reports a configuration to Netbox.

- Airgradient is what Pawprint uses to monitor air quality and PPM in the facility. Integrates well with Home Assistant for visibility.


# Questions & discussion

# Readings & exercises for future meetings