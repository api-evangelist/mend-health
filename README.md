# Mend (mend-health)

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

Mend is a HIPAA-compliant telehealth and patient engagement platform for mental and behavioral healthcare organizations. It powers appointment scheduling and self-scheduling, automated reminders, secure video visits and a virtual waiting room, digital intake forms/consents/assessments, patient messaging, automated payments, and AI no-show prediction. Mend integrates with EHR and practice-management systems through a mix of HL7, SFTP, and an API served from `api.mendfamily.com`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/mend-health/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/mend-health/refs/heads/main/apis.yml)

## Access Model (Important)

Mend operates a **real API** — `api.mendfamily.com` is used by Mend's own portal for session initialization and signaling, and is whitelisted in Mend's own IT onboarding docs (staging is `api-stage.mendvip.com`). However, this is **not an open, self-serve developer platform**:

- There is **no public developer portal** and **no public OpenAPI specification**.
- The API reference lives in a **login-gated customer knowledge base** — the *API Documentation* section at `bestservice.mendfamily.com`, whose detailed articles are visible only to authenticated Mend customers/partners.
- API and EHR integration is provisioned as part of a **commercial engagement** (sales + implementation), typically alongside HL7 and SFTP feeds.

Because of this, the APIs below are documented as **logical capability groupings** with `endpointsModeled: true`. Concrete endpoint paths were **intentionally not fabricated** — they were not confirmed against any public specification.

## Tags

- Telehealth
- Telemedicine
- Patient Engagement
- Behavioral Health
- Scheduling
- Video Visits
- Digital Forms
- HIPAA
- Healthcare

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs (logical, endpoints modeled)

### Mend Appointments and Scheduling API

Creating and managing appointments, provider availability, patient self-scheduling, rescheduling, and automated appointment reminders.

- **Base URL:** `https://api.mendfamily.com`
- **Reference:** [API Documentation (gated)](https://bestservice.mendfamily.com/hc/en-us/sections/360007371714-API-Documentation)
- Endpoints modeled — not confirmed against a public specification.

### Mend Patients API

Creating and syncing patient records, demographics, and contact details between Mend and an external EHR/PMS (via a mix of HL7, SFTP, and the Mend API).

- **Base URL:** `https://api.mendfamily.com`
- **Reference:** [API Documentation (gated)](https://bestservice.mendfamily.com/hc/en-us/sections/360007371714-API-Documentation)
- Endpoints modeled — not confirmed against a public specification.

### Mend Video Visits API

Initializing secure video telemedicine sessions and the virtual waiting room. Real-time media runs over **WebRTC via Vonage TokBox/OpenTok**; `api.mendfamily.com` handles session initialization and signaling. There is no public video endpoint or WebSocket surface on Mend's own API.

- **Base URL:** `https://api.mendfamily.com`
- **Reference:** [API Documentation (gated)](https://bestservice.mendfamily.com/hc/en-us/sections/360007371714-API-Documentation)
- Endpoints modeled — not confirmed against a public specification.

### Mend Digital Forms and Intake API

Assigning digital intake forms, consents, and assessments to patients and returning completed responses to the practice.

- **Base URL:** `https://api.mendfamily.com`
- **Reference:** [API Documentation (gated)](https://bestservice.mendfamily.com/hc/en-us/sections/360007371714-API-Documentation)
- Endpoints modeled — not confirmed against a public specification.

## Plans and Pricing

Pricing is **quote-based and modular**, scaled by organization size, number of caregivers, and selected product families. Third-party directories report provider seats from roughly **$49 per provider per month** with unlimited patients, plus add-on and integration/maintenance fees. API/EHR integration is arranged during the sales and implementation process. See [plans/mend-health-plans-pricing.yml](plans/mend-health-plans-pricing.yml) and [mend.com/pricing](https://mend.com/pricing/).

## Common Properties

- [Website](https://mend.com)
- [LinkedIn](https://www.linkedin.com/company/mendfamily)
- [Documentation (gated API section)](https://bestservice.mendfamily.com/hc/en-us/sections/360007371714-API-Documentation)
- [Plans](plans/mend-health-plans-pricing.yml)

## WebSocket Review

Does Mend expose a documented public WebSocket API? **No.** Real-time video is delivered over WebRTC via Vonage TokBox/OpenTok, not a Mend-owned WebSocket API, and no `ws://`/`wss://` endpoint is documented on Mend's own public API. See [review.yml](review.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
