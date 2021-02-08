the links table powers the portion of the site that links to other state and local COVID resources


the `url` field shoud be obvious

`group` is the category/heading that the link belongs in, generally this is by state (where the states/territories' postal abbreveation is used as the value for this column), but there are some other values in addition to all the postal abbreveations too:
```
USA: National (United States)
ETC: Miscellaneous
```
`description` is an internal description of the resource at that link that is not displayed

`link_type` indicates what general type of resource the link is (testing info, eligibility info, etc.) for deeper categorization in future (not yet implemented)

`public` designates whether the link should be public (i.e. available on the website) or not
