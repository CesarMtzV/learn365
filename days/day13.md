# Nmap - SMB Enumeration
___
Index | Topic
--- | ---
**1** | Summary
**2** | Commands

## Description

- SMB (Server Message block): Protocol that is primarily used for network file sharing and peripheral sharing like printers.
- SMB enumeration often occurs in port 445

## Commands

- OS Enumeration: `nmap -p 445 --script smb-os-discovery TARGET_IP`
- Share Enumeration: `nmap -p 445 --script smb-enum-shares TARGET_IP`
- SMB version and password structure: `nmap -p 445 --script smb-protocols TARGET_IP`