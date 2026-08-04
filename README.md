# Transistor (transistor)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Transistor is a podcast hosting and analytics platform that lets teams host unlimited shows, distribute episodes to Apple Podcasts, Spotify, and YouTube, run private (subscriber-only) podcasts, and measure downloads with advanced analytics. Transistor exposes a documented public REST API at `https://api.transistor.fm/v1` that follows the [JSON:API specification](https://jsonapi.org/), is authenticated with an `x-api-key` header, and covers shows, episodes, analytics, private podcast subscribers, and event webhooks.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/transistor/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/transistor/refs/heads/main/apis.yml)

## Access Model

The Transistor API is a public, self-service REST API available to Transistor account holders. API access is included on all paid plans (Starter and up). You generate an API key in the Account area of your Transistor dashboard and send it on every request in the `x-api-key` header - there is no OAuth flow. The API adheres to the JSON:API specification: it accepts JSON or form-encoded request bodies, returns JSON:API resource objects, and supports sparse fieldsets and included related resources. Requests are rate-limited to **10 requests per 10 seconds**; exceeding the limit returns a `429` and blocks access for 10 seconds. Transistor discourages using the API as a live data source for website content.

## Tags

- Podcasting
- Podcast Hosting
- Analytics
- Media
- Audio
- JSON:API

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

### Transistor Shows API

List and retrieve the podcasts (shows) in your Transistor account and update show metadata. Returns JSON:API resources for each show, including title, description, author, artwork, and distribution details.

- **Human URL:** [https://developers.transistor.fm/#Show](https://developers.transistor.fm/#Show)
- **Base URL:** `https://api.transistor.fm/v1`

#### Tags

- Shows
- Podcasts
- JSON:API

#### Properties

- [Documentation](https://developers.transistor.fm/)
- [API Reference](https://developers.transistor.fm/#Show)
- [OpenAPI](openapi/transistor-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transistor.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transistor.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Transistor Episodes API

Create, list, retrieve, update, and publish podcast episodes. Includes authorizing an audio-file upload, creating draft episodes, and publishing, scheduling, or unpublishing an episode. Episodes are filterable by show, status, and full-text search.

- **Human URL:** [https://developers.transistor.fm/#Episode](https://developers.transistor.fm/#Episode)
- **Base URL:** `https://api.transistor.fm/v1`

#### Tags

- Episodes
- Publishing
- Audio

#### Properties

- [Documentation](https://developers.transistor.fm/)
- [API Reference](https://developers.transistor.fm/#Episode)
- [OpenAPI](openapi/transistor-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transistor.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transistor.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Transistor Analytics API

Retrieve download analytics for a show over a date range, aggregate analytics across all episodes of a show, and per-episode download analytics. Data is returned as JSON:API resources with daily download counts.

- **Human URL:** [https://developers.transistor.fm/#Analytics](https://developers.transistor.fm/#Analytics)
- **Base URL:** `https://api.transistor.fm/v1`

#### Tags

- Analytics
- Downloads
- Metrics

#### Properties

- [Documentation](https://developers.transistor.fm/)
- [API Reference](https://developers.transistor.fm/#Analytics)
- [OpenAPI](openapi/transistor-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transistor.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transistor.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Transistor Subscribers API

Manage private (subscriber-only) podcast subscribers - list, retrieve, add single or batch subscribers with optional email invitations, update a subscriber's email, and remove subscribers. Private feeds gate episode access to authorized subscribers only.

- **Human URL:** [https://developers.transistor.fm/#Subscriber](https://developers.transistor.fm/#Subscriber)
- **Base URL:** `https://api.transistor.fm/v1`

#### Tags

- Subscribers
- Private Podcasts
- Access

#### Properties

- [Documentation](https://developers.transistor.fm/)
- [API Reference](https://developers.transistor.fm/#Subscriber)
- [OpenAPI](openapi/transistor-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transistor.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transistor.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Transistor Webhooks API

Subscribe to and manage event webhooks. Register HTTP callback URLs to receive server-to-server notifications for `episode_created`, `episode_published`, `subscriber_created`, and `subscriber_deleted` events, and list or delete existing webhook subscriptions.

- **Human URL:** [https://developers.transistor.fm/#Webhook](https://developers.transistor.fm/#Webhook)
- **Base URL:** `https://api.transistor.fm/v1`

#### Tags

- Webhooks
- Events
- Notifications

#### Properties

- [Documentation](https://developers.transistor.fm/)
- [API Reference](https://developers.transistor.fm/#Webhook)
- [OpenAPI](openapi/transistor-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transistor.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transistor.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/transistorfm)
- [Website](https://transistor.fm)
- [Documentation](https://developers.transistor.fm/)
- [Plans](plans/transistor-plans-pricing.yml)
- [Rate Limits](rate-limits/transistor-rate-limits.yml)
- [Fin Ops](finops/transistor-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
