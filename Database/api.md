---
---

# General API Documentation


## Rate Limiting

airtable limits the API to 5 requests per second and suggests using a caching server to get anything more than this.

using a GCP f1-micro instance that should theoretically not cost money (or cost very little) we have set up such a caching server at https://api.vacfind.org. 

### Caching server architecture/setup
![VacFind API Data flow diagram](../static/API-Architecture.png)

The caching server uses caddyserver.com to provide HTTPS, varnish to provide the caching, and stunnel as an HTTPS client to make requests to Airtable's API because varnish doesnt support HTTPS or seemingly remote backends very easily.


To be totaly honest, I dont think there is anything about our caching server that limits it to being used for just our airtable bases, so theoretically anyone can use their own base ID and APIkeys to read (not sure how the caching will interact with attempts to write. This may require more configuration) from their own airtable bases.

While we are okay with other COVID-related projcets using our cached API endpoint this way, we may eventually need to restrict the API in some way, or ask that projects that make use of it offer to contribute towards the costs if usage gets too high.
