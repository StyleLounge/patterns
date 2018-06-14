# Application Design

### Decision Tables for Technologies

> Why? There's infinite ways of building a large application. New frameworks, tools and languages emerge constantly. The criteria for a technology decision and the available solutions change all the time.
>
> Decision tables help to visualize trade-offs. For us, decision tables are not about counting pros/cons, but about understanding the trade-offs between options. Spotting trade-offs and having meaningful discussions on them is in the essence of software craftsmanship.
>
> Knowing strengths and weaknesses a finally selected approach helps to anticipate and mitigate future problems.

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



