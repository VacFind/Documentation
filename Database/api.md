---
---

# General API Documentation


## Rate Limiting

airtable limits the API to 5 requests per second. once we start getting close to that, we should start using http://varnish-cache.org/ to cache the requests

## Making it public

After adding ratelimiting, it might be nice to make our API public for other people to use. This would require:

- [ ] Setting up a way for the API to automatically use our Base ID and API Key so people dont need to hardcode it or create their own and have our bases shared with them
- [ ] setting up a subdomain for it (not hard)
- [ ] possibly finding a way to split the cost of the proxy server between API users (maybe we distribute our own API keys?)
