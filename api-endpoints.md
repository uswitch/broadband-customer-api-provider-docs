# Environment URLs
There are production and staging environments, delineated by URL.

Production: https://broadband-customer-api-production.external.usw.co/

Staging: https://broadband-customer-api-staging.external.usw.co/

The staging environment is only used for initial onboarding and testing. It does not contain real customer data.


# Endpoints

### GET /customer

It expects a _?shared_customer_id=_ param and returns all the customer information we agreed to share between Uswitch and the provider. 

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
  ...,
  "shared_journey_id": "example",
  "address": {
    "number": "13",
    "udprn": "5896100055585896",
    "uprn": "15585896",
    "premise": "13",
    "street": "Mand Road",
    "postcode": "NP8 0DU",
    "addressline1": "13 Mand Road",
    "posttown": "London"
  },
  ...
}
```
