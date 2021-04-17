# Nmap - MySQL Enumeration
___
Index | Topic
--- | ---
**1** | Summary
**2** | Commands

## Description

- MySQL is a relational database running on port 3306

## Commands

- Basic MySQL info: `nmap -p 3306 --script mysql-info TARGET_IP`
- User Enumeration: `nmap -p 3306 --script mysql-enum TARGET_IP`
- Check for empty passwords: `nmap -p 3306 --script mysql-empty-password TARGET_IP`
- Brute force password `nmap -p 3306 --script mysql-brute --script-args mysql-brute.threads=100 TARGET_IP`