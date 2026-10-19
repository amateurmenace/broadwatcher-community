# Broadwatcher Community

A broadcast-network console for small studios and community TV stations, for Mac and Windows. It watches a
UniFi network (the gateway, every switch port, the VLANs, the flows that cross the gateway and the port
forwards), talks to Blackmagic gear directly (Web Presenters and HyperDecks over REST, ATEM switchers through
Bitfocus Companion so the switcher's few control slots stay free), and turns it all into one broadcast-health
score with a show profile behind it. A local or cloud AI (an OpenAI-compatible server such as LM Studio, or
Claude with your own key) narrates the verdict and answers questions about the live state.

Broadwatcher is written by Brookline Interactive Group for its own studio; this is the public build, with no
keys and no site-specific devices inside. Downloads are on the **Releases** page.

## What you get

- A home view: the health verdict and score, why, and eight tiles (stream out, stream in, audio, Dante, NDI,
  mics, network, recorders) with ten-minute sparklines.
- A live signal map of internet → gateway → switches → equipment with thin flowing strands for traffic.
- Gateway at a glance: WAN graph, VLAN table, console vitals, biggest flows.
- Streams into the switcher: a stream-intake detector on the switcher's own switch port, source attribution,
  and a **stream path check** for every port forward that points at broadcast gear.
- Switches with every port, what UniFi sees on each port, and your own labels; a find box.
- A roster of broadcast equipment with probes (TCP, Behringer X32 OSC), Blackmagic REST telemetry, standby.
- Show profiles ("Prepare a broadcast"), alerts with plain-language explanations, an event tape, and a phone
  page you can add to your home screen.

## Requirements

- A UniFi console (UDM, UCG, Cloud Key) with the Network application 8 or newer, and an **Integrations API
  key** (UniFi Network > Settings > Control Plane > Integrations). Read-only use.
- Optional: SNMP v2c on the switches for live port counters (Settings > System > Advanced > SNMP).
- Optional: Bitfocus Companion on the same computer for ATEM state (the app reads Companion's HTTP API and
  takes no switcher slot of its own).
- Optional: an OpenAI-compatible local model server, or an Anthropic API key, for the AI verdicts.

## Install

Mac: open the dmg (universal) and drag the app to Applications; the app is not notarised, so the first launch
is right-click > Open. Windows: run the installer or the portable exe; SmartScreen says "Windows protected
your PC": More info > Run anyway.

On first start the Settings screen opens: enter the gateway address and API key, the SNMP community if you
use it, and an AI provider. Then **Edit roster** to add your switcher, recorders, encoders and consoles, and
**Prepare a broadcast** to say what a show expects to be running.

## Privacy

Everything stays on your LAN. The only outside connection is to api.anthropic.com, and only when you choose
Claude as the AI. The UniFi key and any AI key live in your local config file.

## Source

The source lives in a private repository today, together with the station's own configuration. Issues and
questions about the public build are welcome here.
