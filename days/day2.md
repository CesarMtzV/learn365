# Intro de Windows - TryHackMe
___
Index | Topic
--- | ---
**1** | Network Taps
**2** | MAC Floods
**3** | ARP Poisoning
**4** | Basic Filtering

## File system

- PerfLogs: Stores the system issues and other reports regarding performance
- Program Files and Program Files (x86): Is the location where programs install unless you change their path
- Users: In this folder are stored the users created. It also stores user generated data
- Windows - Contains the code to run the OS and some utility tools

## File permissions

- Full control
- Modify
- Read & execute
- List folders content
- Read
- Write
- Special permissions

Tool to check for files or folder permissions: __icacls__. You can use it to check permissions, set ownership of the folder, set, remove or deny permissions

## Local authentication

It's done using the Local Security Authority (LSA), which is a protected subsytem that keeps track of the security policies and the accounts that are on a computer system.

## Types of Active Directory

- On-Premise Active Directory (AD)
- Azure Active Directory (AAD)

## Authentication on AD

Has a record of all users, PCs and Servers and authenticates the users signing in. In an on-premise active directory environment, the authentication can be made by using:

- NTLM / NTLM2
  - Uses a challenge-response sequence of messages between a client and a server system. It does not provide data integrity or data confidentiality protection for the authenticated network connection.
- LDAP / LDAPS
  - The main difference between the two is that LDAPS supports encyrption, and therefore the credentials are not sent in plain text across the network.
  - The Domain Controller can be considered a database of users, groups, cpmputers and so on.
  - Using LDAP/LDAPS the user's workstation sends the credentials using an API to the DC in order to validate them and be able to log in
- KERBEROS
  - Uses symmetric-key cryptography and requires trusted third-party authorization to verify user identitites. 

## Authentication on AAD

AAD is a secure online authentication store. Users have a username and a password which are used when you sign in to an application that uses AAD for authentication.

- SAML (Security Assertion Makrup Language)
  - It's a type of Single Sign-in (SSO) standard. It defines a set of rules/protocols that allow users to access web applilcations with a single login. This is possible because those applications (Service Providers) all trust the systems that verify users' identities (Identity providers)
  - __Service Providers:__ There are the systems and applications that users access throughout the day.
  - __Identity Providers:__ This would be the system that performs user authentication
- OAUTH 2.0
  - Is a standard that apps use to provide client applications with access. It has four important roles:
    - The authorization server
    - The resource owner
    - The client
    - The resource server
- OpenID Connect
  - Is an authentication standard built on top of OAuth 2.0. It adds an additional token called an ID token. It uses simple JSON Web Tokens. It's all about user authentication.


