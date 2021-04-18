# OAuth 2.0
___
Index | Topic
--- | ---
**1** | What is OAuth
**2** | Authorization code grant type
**3** | Implicit grant type
**1** | Reference

## What is OAuth

It's a common authorization framework that enables websites and web applications to request limited access to a user's account on another application.

- OAuth allows user to grant this access without exposing their login credentials to the requesting application.

## Authorization code grant type

1. Authorization request: The client sends a request to the OAuth service's `/auth` endpoint asking for permission
2. User login and consent
3. Authorization code grant: If the user consents to the requested access, their browser will be redirected to the /callback endpoint that was specified in the redirect_uri parameter of the authorization request
4. Access token request: Once the client application receives the authorization code, it needs to exchange it for an access token.
5. Access token grant
6. API call: Now the client application has the access code, it can finally fetch the user's data from the resource server. 
7. Resource grant

## Implicit grant type

Rather than first obtaining an authorization code and then exchanging it for an access token, the client application receives the access token immediately after the user gives their consent.

1. Authorization request
2. User login and consent
3. Access token grant
4. API call
5. Resource grant

## Reference

[Link to Portswigger](https://portswigger.net/web-security/oauth)
[OAuth grant types](https://portswigger.net/web-security/oauth/grant-types)