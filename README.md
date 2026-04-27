# FOAF Foundation documentation

This repository contains the documentation site for the FOAF (Friend of a Friend) Foundation, served at [docs.foaf.foundation](https://docs.foaf.foundation).

FOAF is an open protocol for community-scale mutual credit. Trustlines between known parties handle the accounting; multi-hop payments route through the trust graph; debts circulate and cancel through credit loops rather than requiring settlement in money from outside the system.

The first application built on the protocol, GrowOperative, is in soft launch in Crawford Bay, BC. The protocol's eventual home is Radix Babylon.

## What this site covers

- The FOAF Foundation, its structure, and tokenomics
- GrowOperative as the reference client
- Protocol architecture, both current and the long-term peer-to-peer direction
- Governance and the move toward a Marshall Islands DAO
- How to collaborate on building the protocol stack

## Contributing to the docs

Site is built with [MkDocs](https://www.mkdocs.org/) and the [Material theme](https://squidfunk.github.io/mkdocs-material/). Local preview via Docker:

```
docker run --rm -p 8000:8000 -v "$(pwd):/docs" squidfunk/mkdocs-material serve -a 0.0.0.0:8000
```

Then open http://localhost:8000. The site live-reloads on file save.

To propose changes, fork this repo, edit the markdown in `docs/`, and open a pull request. See the [contribution guide](./docs/community/contribution.md) for the longer version.

## Getting involved beyond docs

If you're interested in building the protocol itself rather than the docs, see [Build with us](./docs/technical/build-with-us.md) for the three current role tracks: the Hyperlane bridge, the Scrypto protocol stack, and the peer-to-peer architecture.
