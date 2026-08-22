# Wawanesa Insurance (wawanesa)

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
