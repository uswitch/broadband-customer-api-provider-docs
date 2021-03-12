# Authentication
Access to the API is controlled using temporary JSON Web Tokens (JWT).

Before using the API, you will be issued with two pieces of information, a **Client ID** and a **Client Secret**. These are used to obtain tokens.


## Step 1 — Fetch an access token
Request an access token as per the example below.

Authentication URL: https://uswitchsuppliers.eu.auth0.com/oauth/token

**Set audience as follows:**

Staging: https://broadband-customer-api-staging.external.usw.co

Production: https://broadband-customer-api-production.external.usw.co


Using your **Client ID** and **Client Secret** in place of **CLIENT_ID** and **CLIENT_SECRET** below, make a request to obtain a fresh token.

```
curl --request POST \
  --url https://uswitchsuppliers.eu.auth0.com/oauth/token \
  --header 'content-type: application/json' \
  --data '{"client_id":"CLIENT_ID","client_secret":"CLIENT_SECRET","audience":"https://broadband-customer-api-production.external.usw.co","grant_type":"client_credentials"}'
```
    
This will return JSON containing the token.
```
 {
  "access_token": "eyJhbGciOiJSUzI1NiIsInR5c...",
  "token_type": "Bearer"
}
   
```

## Step 2 — Use the token to access the API
The access token retrieved in the previous step is added to all requests to the API in the headers. Specifically it goes in the Authorization header, as a Bearer token. In the URL, you should replace ENDPOINT with the specific name of the endpoint you are using.

```
curl https://broadband-customer-api-production.external.usw.co/ENDPOINT \
  -H "Accept: application/json"                       \
  -H "Content-Type: application/json"                 \
  -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5c..."
```

## Expired tokens
Tokens will need to be refreshed on a regular basis. The exact time may vary, but they will generally be valid for several hours. It is recommended to keep track of the token’s time-to-live within your application. If you attempt to access the API with an expired token, it will return the 401 HTTP status code.

## How is the token secured?
The token contains your identity and a request for access to the API. You can see the token contents by decoding it (for example, by using the site https://jwt.io). It is signed by the authorisation service using the RS256 cryptographic algorithm, and this will verified by our API to check it is valid and has not been altered. This ensures that the tokens cannot be faked, and no other parties can gain access to your customers’ information.

As the API uses HTTPS, the token will encrypted during transfer to the API.

## What are my Client ID and Client Secret?
They are alpha-numeric keys that we will generate for you during onboarding. You will need to keep track of these in order to request access tokens. Since it controls access to your customers’ personal data, take care not to lose your Client Secret, or expose it publicly. It should not be checked into version control. If it is lost, we can invalidate it immediately.
