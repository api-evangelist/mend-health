# Mend (mend-health)

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
