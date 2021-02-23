---
---
# Tutorials, Advice, and Ideas

heres a page with instructions tha tmay be helpful for other people trying to create COVID Vaccine tracking apps


## Tutorial: Finding other COVID-relief projects using bulk domain name lookup tools

This documentation is now maintained on our [BeastMode](https://github.com/VacFind/BeastMode) Repo.

## How to Mitigate the effects of service downtime

With some recent incidents of AirTable going down and our [admittedly imperfect caching API](./Database/api), here are some things (in no particular order) you can do to limit the effects of services or API's being down:

### Stop using airtable embeds if you can.
If airtable goes down, all your embeds will show an ugly plaintext "Service Unavailable" message.

### Client Side Caching
While using a caching server to speed up requests is nice, having the caching server go down can still ruin your day and break your app. 

This is why its ideal to also have multiple layers of caching. As an example, [our caching API](./Database/api#varnish) can help protect against airtable going down by serving cached requests. But now if our caching server goes down at 2 am and we are asleep and cant fix it, our access to data is still broken.

This is why we also [cache data to the browsers storage](https://github.com/VacFind/VacFind-site/commit/ada7fafc42e595e3087fcfddf0c7c6cf61d1df3c) so that anyone who has visited our site at least once since this change was deployed is able to see a slightly older version of our list of other similar projects while fresh results are fetched from the API. This works particularly well since our data doesnt change that often and isnt as important if its wrong compared to data on available vaccination sites. However, this technique can still be used to cache partial data that doesnt update as often, like the names and locations of vaccination sites so that *something* can be displayed to users, even if all the information isnt available immediately.


