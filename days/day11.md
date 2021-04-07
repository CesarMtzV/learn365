# OpenVAS - TryHackMe
___
Index | Topic
--- | ---
**1** | Description
**2** | GVM Framework
**3** | Run OpenVAS with docker


## Description

- OpenVAS is an application used to scan endpoints and web applications to identify and detect vulnerabilities.
- OpenVAS is a service within a larger framework of services known as Greenbone Vulnerability Management (GVM)

## GVM Framework

The framework can be broken down into three sections:
- Front-End
  - This is what you interact with when you navigate to OpenVAS in your browser
- Back-End
  - Its the infraestructure that will be actually conducting all of the vulnerability scanning and processing data and NVTs though OpenVAS and GVM.
  - GVM is the middle man between the scanners and the front-end
- Vulnerability/Information
  - Contains all the info and vulnerability tests that come from the Greenbone Community Feed that will be the mian baseline for testing against systems.

## Run OpenVAS with docker

- Command: `docker run -d -p 443:443 --name openvas mikesplain/openvas`
- Navigate to: `https://127.0.0.1`
- Login with `admin:admin`

