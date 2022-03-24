# Erd-talk

Erd-talk is a web-of-trust/reputation system for URIs.

1. URIs can be assigned key/values, e.g. "example.com:trust:1.0"
2. You can query friendly erd-talk clusters for their values and compute against them, e.g. "Gather all the trust values from friends about URI x and return the average"
3. You can handle queries in a custom way.  Instead of just returning a value, you can compute, or recursively (via friendly clusters) compute, a new value.

What can erd-talk be used for?

- Reweight Amazon/Yelp reviews according to your friends/family.
- Discover new or interesting websites
- Help decide whether a program/website/business is trustworthy or not
- Calculate impact scores of papers independent of publishers
- Find inaccuracies in news stories
