# Application Design

### Decision Tables for Technologies

> Why? There's infinite ways of building a large application. Every few weeks new frameworks, tools, languages are being made available in the various stacks and ecosystems. Both the criteria for a technology decision and the available solutions change continuously. It's not about constantly changing a company's stack. Knowing strengths and weak spots of the  approaches, languages, frameworks and paradigms used results in much better decision right from the design phase.

### The Walking Skeleton

> Why? A lot of underestimated complexity lurks in the integration phase of a user story. The idea of the walking skeleton is to tackle that part first and add the business logic later. It makes planning and estimations more reliable.

* [alistair.cockburn.us/Walking+skeleton](http://alistair.cockburn.us/Walking+skeleton)

### Canonical Names

> Why? Accronyms and abbreviations are fun while inventing them but they don't scale. That means that the bigger a system gets the harder it is to transfer knowledge about what means what to the entire team and especially new members.

##### Examples \(the actual pattern is highly

```
p-tracking-admin-endpoint-de-1
# An endpoint of the tracking component that provides administrative functionality.
# It might exist for staging (s) but this one is running in production (p) in Germany (de).
# Also it might be clustered behind a load balancer, hence the index (1)

s-product-importer-feed-fetcher-us-3
# A service within the product-importer component that fetches feeds from somewhere in
# the world it's the product-importer-feed-fetcher that is deployed to the US staging
# stage and apparently it's instances 3 within a cluster.
```



