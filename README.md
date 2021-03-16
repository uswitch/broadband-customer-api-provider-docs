# Broadband customer API
Our API provides partners with the means to access customer journey data from Uswitch. 
We want to give customers the best possible experience of switching their broadband. This API aims to reduce the duplication of data capture on both Uswitch and Provider sites, if a customer needs to give us an address and the provider will also need that address we will use this API to share data accross so the user has a smoother experience.

![image](https://user-images.githubusercontent.com/2581278/110932740-c8bf3400-8323-11eb-9027-4015c9fce6e5.png)

[high level sequence diagram](https://sequencediagram.org/index.html?presentationMode=readOnly#initialData=C4S2BsFMAIAkQOYAsoDdLmgZ0gRwK6QB2AxjAGbgD2A7gFB0CGJwVATtPjm3QA6NtQJEPyLBOWGmBJIAtOTZUxxACZ8BQkYzHRG5ciHAhGwSLKKRgNdgGt1gkMNHjei1CBWQe-B0+3jGfGA5bncye01naBIuVgBbL1lGXhAGOi5EgD4uKWAZeUVlIhUALgQQdCwJXRUVNkgsKu0VbAxIFiboVyoVfBZ0yWk5BSVTYtlMmKx4xOSQEpwY+vAAT2xWeokvaBAicipdBEZd6d1sJAFIFoArKnw2CzWPaAAKbGvngEoB3PyRopUEz0BiMJjMFisthK-Ea0CU72eu2gwRgAEUAMpMfSGYymcyWaxsGwTbruTxsaGMWHwrAfFpIlHQDEMUkeLKBYKyUKOSAleoEBoBZFUGzEJgsCpg3RBEJeMKQJgyrlynkktxsikISzQABGzBsZ1YoqIdE8zFAqClHNlbHlLPV5ImUxmbCSKQWqmFxt0xQRanNktM0ViVASrrmdGdodmKTVVDJXjK2r1JANGQ4u32bDiJhASlNkADlqDUbDbtSQA)


# How does it work?
Our API makes available information about the customers you have acquired through Uswitch, meaning it can be consumed by your systems programmatically. It operates on a ‘pull’ pattern — we make the data available, and your application retrieves it. 

If you're an developer integrating with our API, we suggest reading the following: 
- [Authentication guide](https://github.com/uswitch/broadband-customer-api-provider-docs/blob/main/Authentication.md) for how to authenticate
- [API endpoints](https://github.com/uswitch/broadband-customer-api-provider-docs/blob/main/api-endpoints.md) for how to query our endpoints


# How do I join?
There is an onboarding proccess we need to follow in order to give you access to our API. Contact any member from the Commercial team and they should be able to help you get started.

# Is it secure?
All data is encrypted using industry best-practice standards while in transit. Your customers’ data will only ever be visible to you, and is secured with your secret key. If you lose your key, we can immediately invalidate it, and issue you with a new one.
