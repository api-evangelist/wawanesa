# Wawanesa Insurance (wawanesa)

The Wawanesa Mutual Insurance Company, founded in 1896 in Wawanesa, Manitoba and headquartered in Winnipeg, is one of Canada's largest property and casualty mutual insurers, writing auto, home, condo, tenant, seasonal residence, farm and commercial lines across every province and territory through a 100% independent broker distribution model, alongside its wholly-owned life and group subsidiary Wawanesa Life. Wawanesa runs its policy, claims and billing on Guidewire InsuranceSuite following a roughly $300 million Strategic Systems Renewal that made it one of the first Canadian insurers to put its entire product suite online, and it has announced a broker-facing API programme — most notably a Commercial Small Business API aligned to CSIO data standards that supports real-time rating, quoting and binding — plus CSIO My Proof of Insurance electronic pink slips. None of that surface is public.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/wawanesa/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/wawanesa/refs/heads/main/apis.yml)

## API Posture

Wawanesa publishes **no developer portal, no API reference, no OpenAPI definition, no Postman collection, no GraphQL endpoint and no webhook catalog.**

- `developer.wawanesa.com`, `developers.wawanesa.com` and `docs.wawanesa.com` do not resolve.
- `api.wawanesa.com` exists but answers **403 Forbidden** (nginx) at the root; `/health` returns plain-text `OK`. Every spec path probed (`/openapi.json`, `/openapi.yaml`, `/swagger.json`, `/api-docs`, `/v1/openapi.json`) returns 403.
- `wawanesa.com/developers`, `/api`, `/developer`, `/partners` and `/integrations` all return 200 only because the site serves a **catch-all redirect** to `/us/` — none are real pages.
- The only integration surface reachable on the open internet is the **Broker Platform** at [brokerplatform.wawanesa.com](https://brokerplatform.wawanesa.com/) (Salesforce Experience Cloud) behind an **Okta login wall** at [login.brokerplatform.wawanesa.com](https://login.brokerplatform.wawanesa.com/).

Onboarding for the broker API is explicitly human: *"Brokers looking to integrate Wawanesa's new Commercial API into their operations can contact their Wawanesa Business Development representative."*

## Standards Posture

**No ACORD reference found.** Wawanesa's own site search for `ACORD` returns *"No results found for keyword ACORD"*. Canada's broker-connectivity standards body is **CSIO** (Centre for Study of Insurance Operations), which plays the role IVANS and ACORD AL3 play in the United States, and Wawanesa names it repeatedly:

- The Commercial Small Business API is *"fully aligned with CSIO data standards"* and *"aligns with CSIO Commercial Small Business Standards"* (2022-03-30).
- Wawanesa implemented **CSIO My Proof of Insurance** electronic pink slips in Alberta, Ontario and Nova Scotia (2020-01-20).
- Wawanesa takes *"a leadership role in the Insurance Brokers Association of Canada's D/X initiative"* (2022-03-28).

## Insurance Verbs

| Verb | Exposed | Audience |
| --- | --- | --- |
| Quote | Yes (undocumented) | Independent brokers only |
| Bind | Yes (undocumented) | Independent brokers only |
| Issue | No public API | — |
| FNOL / Claims | No public API | Consumer web form + gated broker platform |

## Tags

- Insurance
- Canada
- Property and Casualty
- Carrier
- Mutual Insurer
- Broker
- Commercial Lines
- Personal Lines
- Underwriting
- Claims
- Policy Administration
- CSIO
- Partner Gated

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## APIs

### Wawanesa Commercial Small Business API

Broker-facing commercial small business API announced by Wawanesa on 2022-03-30, built with HUB International and described by Wawanesa as "fully aligned with CSIO data standards". Per the company announcement it lets brokers connect their information systems to Wawanesa for real-time risk rating, quoting and binding, with tailored packages for Business & Professional Services, Retail Services and Contractors. There is no public developer portal, no published API reference, no OpenAPI definition and no documented base URL.

- **Human URL:** [https://www.wawanesa.com/canada/news/wawanesa-improves-insurance-quotes-for-small-businesses](https://www.wawanesa.com/canada/news/wawanesa-improves-insurance-quotes-for-small-businesses)
- **Base URL:** not published

#### Tags

- Insurance
- Commercial Lines
- Small Business
- Quote
- Bind
- Rating
- Broker
- CSIO
- Partner Gated

#### Properties

- [Documentation](https://www.wawanesa.com/canada/news/wawanesa-improves-insurance-quotes-for-small-businesses)
- [Partner Portal](https://brokerplatform.wawanesa.com/)
- [Authentication](https://login.brokerplatform.wawanesa.com/.well-known/openid-configuration)

## Common Properties

- [Website](https://www.wawanesa.com/canada/)
- [Blog](https://www.wawanesa.com/canada/blog/)
- [News](https://www.wawanesa.com/canada/news/)
- [Partner Portal](https://brokerplatform.wawanesa.com/)
- [Login](https://login.brokerplatform.wawanesa.com/)
- [Customer Portal](https://membercentre.wawanesa.com/)
- [Contact](https://www.wawanesa.com/canada/contact-us/inquiries-and-feedback.html)
- [Privacy Policy](https://www.wawanesa.com/canada/pip/about-privacy.html)
- [Terms of Service](https://www.wawanesa.com/canada/pip/terms-and-conditions.html)
- [Careers](https://www.wawanesa.com/jobs/)
- [LinkedIn](https://www.linkedin.com/company/wawanesa-insurance)
- [Twitter](https://twitter.com/wawanesa)
- [Facebook](https://www.facebook.com/wawanesainsurance)
- [YouTube](https://www.youtube.com/c/wawanesa)
- [Instagram](https://instagram.com/wawanesacanada)

## Review

See [review.yml](review.yml) for the full API Evangelist reviewer finding, including every probed URL with its HTTP status, the OpenID Connect discovery documents behind the broker login, and the CSIO/ACORD standards evidence.

## Maintainers

- Kin Lane — kin@apievangelist.com
