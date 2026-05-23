# Gopuff (gopuff)

Gopuff is a private quick-commerce company headquartered in Philadelphia that operates its own network of micro-fulfillment centers to deliver everyday essentials — snacks, beverages, household goods, fresh items, alcohol, and over-the-counter medicines — to consumers in roughly 15 to 30 minutes. Beyond its direct-to-consumer mobile app and website, Gopuff exposes its instant-delivery infrastructure to brands and retailers through the **Powered by Gopuff** platform, which offers a Shopify Fulfillment app, a white-labeled Storefronts theme, and a partner Developer Portal backed by HTTP APIs. Gopuff also operates a Delivery Partner program with its own driver pay portal, scheduling UI, and ID-scanning flow (alcohol delivery uses the Microblink BlinkID SDK that Gopuff forks on GitHub).

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/gopuff/refs/heads/main/apis.yml)

## Scope

- **Type:** Contract
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Quick Commerce, Instant Delivery, Last Mile, Grocery, Fulfillment, Retail, Logistics

## Timestamps

- **Created:** 2026-05-22
- **Modified:** 2026-05-23

## APIs

### Powered by Gopuff Fulfillment API

The Powered by Gopuff Fulfillment API is the partner-facing HTTP surface used by Gopuff's Shopify Fulfillment app and white-labeled Storefronts theme to determine whether a consumer is inside a Gopuff micro-fulfillment center (MFC) delivery zone, to check real-time product availability at the local MFC, to surface carrier rates at Shopify checkout, and to route orders from the merchant's storefront to Gopuff for picking, packing, and delivery. Detailed reference documentation is published as "coming soon" at the partner docs site; the base URL `https://fulfillment-api-eus.partners.gopuff.com/shopify/v1/shops` is wired into the Shopify app embed as the canonical entry point and is the only publicly documented host.

- **Human URL:** [https://docs.poweredbygopuff.com/](https://docs.poweredbygopuff.com/)
- **Base URL:** `https://fulfillment-api-eus.partners.gopuff.com/shopify/v1`

#### Tags

- Fulfillment, Instant Delivery, Shopify, Quick Commerce, Last Mile

#### Properties

- [Documentation](https://docs.poweredbygopuff.com/)
- [SignUp](https://poweredby.gopuff.com/)
- [OpenAPI](openapi/gopuff-fulfillment-openapi.yml)
- [Naftiko Capability — Zones](capabilities/fulfillment-zones.yaml)
- [Naftiko Capability — Availability](capabilities/fulfillment-availability.yaml)
- [Naftiko Capability — Orders](capabilities/fulfillment-orders.yaml)

### Powered by Gopuff Storefronts API

Storefronts Powered by Gopuff is a customizable Shopify theme integrated with Gopuff's catalog and delivery APIs that enables brands to launch a white-labeled DTC website with built-in 15-minute delivery from a Gopuff MFC. The same partner platform exposes three documented integration calls: a delivery-zone check invoked when a customer enters their address, a per-MFC inventory-availability lookup driven by SKU/UPC mapping, and an order-routing call that hands the completed checkout to the nearest MFC for fulfillment.

- **Human URL:** [https://poweredby.gopuff.com/pages/storefronts](https://poweredby.gopuff.com/pages/storefronts)
- **Base URL:** `https://fulfillment-api-eus.partners.gopuff.com/shopify/v1`

#### Tags

- Storefronts, Shopify, DTC, Quick Commerce, Catalog

#### Properties

- [Documentation](https://poweredby.gopuff.com/pages/storefronts)
- [SignUp](https://poweredby.gopuff.com/)

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

## Artifacts

| Type | Path |
|---|---|
| OpenAPI | [openapi/gopuff-fulfillment-openapi.yml](openapi/gopuff-fulfillment-openapi.yml) |
| Naftiko Capabilities | [capabilities/](capabilities/) — `fulfillment-zones`, `fulfillment-availability`, `fulfillment-orders` |
| JSON Schema | [json-schema/](json-schema/) — delivery zone, product availability, order |
| JSON Structure | [json-structure/gopuff-order-structure.json](json-structure/gopuff-order-structure.json) |
| JSON-LD | [json-ld/gopuff-context.jsonld](json-ld/gopuff-context.jsonld) |
| Examples | [examples/](examples/) — zone check, availability, carrier rate, create order, get order |
| Spectral Rules | [rules/gopuff-fulfillment-rules.yml](rules/gopuff-fulfillment-rules.yml) |
| Vocabulary | [vocabulary/gopuff-vocabulary.yml](vocabulary/gopuff-vocabulary.yml) |
| Plans | [plans/gopuff-plans-pricing.yml](plans/gopuff-plans-pricing.yml) |
| Rate Limits | [rate-limits/gopuff-rate-limits.yml](rate-limits/gopuff-rate-limits.yml) |
| FinOps | [finops/gopuff-finops.yml](finops/gopuff-finops.yml) |

## Notes

- Powered by Gopuff is only available to brands whose products are already merchandised on the Gopuff consumer platform.
- Pre-negotiated delivery rates are surfaced at Shopify checkout as `Instant Delivery - Powered by Gopuff`; merchants cannot add handling fees on top.
- Gopuff handles all delivery-related customer service for orders fulfilled through the partner platform; merchants only handle product-related issues.
- The Gopuff GitHub org (`github.com/gopuff`) contains 20 repos: internal Azure / Snowflake / Meltano data tooling, a fork of Microblink `blinkid-ios` for in-app ID scanning during alcohol delivery, `healthz` (health-check library), `timecapsule` (feature time-boxing), `morecontext` (Go context helpers), and a small set of React Native UI components. No public SDK for the Powered by Gopuff partner API has been published.
- The partner API reference at `docs.poweredbygopuff.com/api-reference.md` is currently published as "coming soon"; the OpenAPI in this repo reconstructs the documented surfaces (shops, zones, availability, rates, orders) from the partner Help Center and operational behavior of the Shopify app.
