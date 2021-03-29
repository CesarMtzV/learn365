# Wireshark 101 - TryHackMe

This repository contains my learning path in the Learn 365 challenge, which consists in keep learning something for 365 days. The main topics are Cybersecurity and Web Dev, but sometimes I'll focus on something different to change things up.

___
Index | Topic
--- | ---
**1** | Network Taps
**2** | MAC Floods
**3** | ARP Poisoning
**4** | Basic Filtering

## Network Taps

They are a physical implants in which you can tap between a cable to sniff and capture packets. 
Two primary ways to tap a wire:
- __Vampire:__ Hardware that can tap the wire and intercept traffic as it comes across
- __Inline network tap:__ You place it between two network devices. The tap will replicate packets as they pass the tap. Example: __Throwing Star LAN Tap__

## MAC Floods

Is an attack in which the attacker fills the CAM table of the switch. Once the switch has its CAM table filled, it can no longer accept more MAC addresses, so it will start to send packets to all ports of the switch.

## ARP Poisoning

Redirect the traffic from the host to the machine you're monitoring from.

## Basic filtering

- IP: `ip.addr == <IP Address>`
- SRC and DST `ip.src == <SRC> and ip.dst == <DST>`
- Port and protocol: `tcp.port eq <Port> or <Protocol Name>`
- Opcode: `arp.opcode == X`

