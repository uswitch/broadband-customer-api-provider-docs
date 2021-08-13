# Environment URLs
There are production and staging environments, determined by URL.

Production: https://broadband-customer-api-production.external.usw.co/

Staging: https://broadband-customer-api-staging.external.usw.co/

The staging environment is only used for initial onboarding and testing. It does not contain real customer data.

# Endpoints

### GET /customer

It expects a _?sharedJourneyId=_ param and returns agreed customer information collected on Uswitch for the provider. 

**Example request:**
```
curl --request GET \
     --header 'authorization: Bearer eyJ0eXAiO...Redacted...' \
     --url 'https://broadband-customer-api-staging.external.usw.co/customer?shared_journey_id=mock'
```


**Example response:**
_https://broadband-customer-api-staging.external.usw.co/customer?shared_journey_id=mock_

```
{
  "sharedJourneyId": "UUIDv1",
  "address": {
    "summaryLine": "Flat 10, Ambassador Court, 30 Inglewood Road, London, NW6 1RY",
    "addressLine1": "Flat 10, Ambassador Court",
    "addressLine2": "30 Inglewood Road",
    "postTown": "London",
    "postcode": "NW6 1RY",
    "udprn": "17725535",
    "uprn": "5061682",
  },
  ...
}
```
