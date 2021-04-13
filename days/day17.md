# Kerberos
___
Index | Topic
--- | ---
**1** | Description
**2** | Terminology

## Description

Kerberos is the default user authentication service for Microsoft Windows domains. It is intended to be more "secure" than NTLM by using third party ticket authorization as well as stronger encryption.

## Terminology

- Ticket Granting Ticket (TGT)
  - Authentication ticket used to request service tickets from the TGS for specific resources from the domain
- Key Distribution Center (KDC)
  - Is a service for issuing TGTs and service tickets that consist of the Authentication Service and the Ticket Granting System
- Authentication Service
  - Issues TGTs to be used byu the TGS in the domain to request access to other machines and service tickets
- Ticket Granting Service (TGS)
  - Takes the TGT and returns a ticker to a machine in the domain
- Service Principal Name (SPN)
  - An identifier given to a service instance to associate a service instance with a domain service account. Windows requires that services have a domain service account which is why a service needs an SPN set.
- KDC Long Term Secret Key (KDC LT Key)
  - The KDC key is based on the KRBTGT service account. It is used to encrypt the TGT and sign the PAC
- Client Long Term Secret Key (Client LT Key)
  - The client key is based on the computer or service account. It is used to check the encrypted timestamp and encrypt the session key.
- Service Long Term Secret Key (Service LT Key)
  - The service key is based on the service account. It is used to encrypt the service portion of the service ticket and sign the PAC.
- Session Key
  - Issued by the KDC when a TGT is issued. The user will provide the session key to the KDC along with the TGT when requesting a service ticket.
- Privilege Attribute Certificate (PAC)
  - The PAC holds all of the user's relevant information, it is sent along with the TGT to the KDC to be signed by the Target LT Key and the KDC LT Key in order to validate the user.