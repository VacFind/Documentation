---
---

# Links Table

The links table powers the portion of the site that links to other state and local COVID resources. in no particular order:


## `url`
the URL of this link, ideally starting with `https://`


## `group`
represents the heading that the link belongs under on the vacFind site, this mostly represents what state/region the resource is for (where the states/territories' postal abbreveation is used as the value for this column), but there are some other values in addition to all the postal abbreveations too:
```
USA: National (United States)
ETC: Miscellaneous
INTL: International
```

If this field is blank, category can be assumed to be the same as "Miscellaneous"

This field may eventually become a "location" field so that it can better support international links

## `category`
This single-select category helps divide up the different types of links stored in the database. Examples include:
- `government resource` for sites run by government entities
- `volunteer project` for projects created/run by volunteers
- `dev resource` for resources that may be interesting to volunteers and/or developers when creating new tools
- `useless` non-covid or otherwise useless resources. these include things like domains that redirect to non-covid places that really only serve as a record of what sites `not` to visit

this may be removed later due to the risk of API consumers accidentally promoting these sites

## `description`
is an internal description of the resource at that link that is not displayed, this is useful for adding comments and things

## `tags`
allows resources to be tagged

This is a multi-select list in airtable that has options like `vaccination`, `testing`, and `eligibility` . This makes it easy to specify what resource a link points to.

## `link_title`
a user-facing title to give the link in case it is a long link that may not be good to display on screen directly

## `public`
designates whether the link should be public (i.e. available on the website) or not

## `source_url`
internal text field for documenting where a link was found if it was discovered through another link (like a reddit post or news article). not currently used but may be handy in future

## `verification_status`
how trustworthy is the link? currently the main values are `government resource` and `reported in media` as vacFind isnt really able to do super detailed investigations on each and every project. `unverified` is also used to mark stuff thats verified, but most links to projects are deemed trustworthy by default

there may be a `trust` field to either augment or replace this in future


## `data_collection_format`
a list of tags representing how this source collects their data (if known), values include things like `calls`, `scraping`, `crowdsource`, `api`

## `data_provided_format`
list of tags representing what formats this source provides data to others in. see `data_collection_format` for some possible options


If you have data to add to this list