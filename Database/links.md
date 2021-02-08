the links table powers the portion of the site that links to other state and local COVID resources


the `url` field shoud be obvious

`group` is the category/heading that the link belongs in, generally this is by state (where the states/territories' postal abbreveation is used as the value for this column), but there are some other values in addition to all the postal abbreveations too:
```
USA: National (United States)
ETC: Miscellaneous
```
## `description`
is an internal description of the resource at that link that is not displayed

## `link_type`
indicates what general type of resource the link is for deeper categorization in future.

This is implemented using a multi-select list that has options like `vaccine`, `testing`, and `eligibility` as well as options like `tool`, `information`, `statistics`. This makes it easy to specify what type of link something is. For example, a state's vaccine information page could just be labelled `information`, and a vaccine locating tool could be labelled as `vaccine`, and `tool`. This makes it easy to display links in particular categories


## `public`
designates whether the link should be public (i.e. available on the website) or not