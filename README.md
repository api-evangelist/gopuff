# Gopuff (gopuff)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Gopuff is a private quick-commerce company headquartered in Philadelphia that operates its own network of micro-fulfillment centers to deliver everyday essentials — snacks, beverages, household goods, fresh items, alcohol, and over-the-counter medicines — to consumers in roughly 15 to 30 minutes. Beyond its direct-to-consumer mobile app and website, Gopuff exposes its instant-delivery infrastructure to brands and retailers through the Powered by Gopuff platform, which offers a Shopify Fulfillment app, a white-labeled Storefronts theme, and a partner Developer Portal backed by HTTP APIs (e.g. fulfillment-api-eus.partners.gopuff.com). Gopuff also operates a Delivery Partner program with its own driver pay portal, scheduling UI, and ID-scanning flow (alcohol delivery uses the Microblink BlinkID SDK).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/gopuff/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/gopuff/refs/heads/main/apis.yml)

## Scope

- **Type:** Contract

## Tags

- Quick Commerce
- Instant Delivery
- Last Mile
- Grocery
- Fulfillment
- Retail
- Logistics

## Timestamps

- **Created:** 2026-05-22
- **Modified:** 2026-05-23

## APIs

### Powered by Gopuff Fulfillment API

The Powered by Gopuff Fulfillment API is the partner-facing HTTP surface used by Gopuff's Shopify Fulfillment
app and white-labeled Storefronts theme to determine whether a consumer is inside a Gopuff micro-fulfillment
center (MFC) delivery zone, to check real-time product availability at the local MFC, to surface carrier
rates at Shopify checkout, and to route orders from the merchant's storefront to Gopuff for picking, packing,
and delivery. Detailed reference documentation is published as "coming soon" at the partner docs site; the
base URL `https://fulfillment-api-eus.partners.gopuff.com/shopify/v1/shops` is wired into the Shopify app
embed as the canonical entry point and is the only publicly documented host.

- **Human URL:** [https://docs.poweredbygopuff.com/](https://docs.poweredbygopuff.com/)
- **Base URL:** `https://fulfillment-api-eus.partners.gopuff.com/shopify/v1`

#### Tags

- Fulfillment
- Instant Delivery
- Shopify
- Quick Commerce
- Last Mile

#### Properties

- [Documentation](https://docs.poweredbygopuff.com/)
- [Sign Up](https://poweredby.gopuff.com/)
- [OpenAPI](openapi/gopuff-fulfillment-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/gopuff-fulfillment.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/gopuff-fulfillment.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Powered by Gopuff Storefronts API

Storefronts Powered by Gopuff is a customizable Shopify theme integrated with Gopuff's catalog and delivery
APIs that enables brands to launch a white-labeled DTC website with built-in 15-minute delivery from a
Gopuff MFC. The same partner platform exposes three documented integration calls: a delivery-zone check
invoked when a customer enters their address, a per-MFC inventory-availability lookup driven by SKU/UPC
mapping, and an order-routing call that hands the completed checkout to the nearest MFC for fulfillment.
Public reference docs are not yet published; only the operational contract documented in the partner help
portal is available.

- **Human URL:** [https://poweredby.gopuff.com/pages/storefronts](https://poweredby.gopuff.com/pages/storefronts)
- **Base URL:** `https://fulfillment-api-eus.partners.gopuff.com/shopify/v1`

#### Tags

- Storefronts
- Shopify
- DTC
- Quick Commerce
- Catalog

#### Properties

- [Documentation](https://poweredby.gopuff.com/pages/storefronts)
- [Sign Up](https://poweredby.gopuff.com/)
- [Postman Collection](collections/gopuff-fulfillment.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/gopuff-fulfillment.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Homepage](https://www.gopuff.com)
- [Newsroom](https://www.gopuff.com/newsroom)
- [Careers](https://www.gopuff.com/go/careers)
- [Help Center](https://help.gopuff.com/)
- [Partner Portal](https://poweredby.gopuff.com/)
- [Partner Documentation](https://docs.poweredbygopuff.com/)
- [Developer Portal](https://devportaldocs.poweredbygopuff.com/)
- [Shopify App](https://apps.shopify.com/powered-by-gopuff)
- [Delivery Partner Sign Up](https://deliver.gopuff.com/signup)
- [Delivery Partner Pay Portal](https://driver-pay.gopuff.com/)
- [Delivery Partner Scheduling](https://driver-scheduling-manager-ui.delivery-tech.gopuff.com/)
- [Driver App](https://www.gopuff.com/go/apps)
- [Google Play Driver App](https://play.google.com/store/apps/details?id=com.gopuff.godrive2.live)
- [GitHub Organization](https://github.com/gopuff)
- [LinkedIn](https://www.linkedin.com/company/gopuff)
- [JSON-LD](json-ld/gopuff-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [JSON Schema](json-schema/gopuff-delivery-zone-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/gopuff-product-availability-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/gopuff-order-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Vocabulary](vocabulary/gopuff-vocabulary.yml)
- [Spectral Ruleset](rules/gopuff-fulfillment-rules.yml)
- [Plans](plans/gopuff-plans-pricing.yml)
- [Rate Limits](rate-limits/gopuff-rate-limits.yml)
- [Fin Ops](finops/gopuff-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
