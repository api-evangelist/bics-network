# BICS (bics-network)

BICS is an international communications enabler and wholesale carrier, part of Proximus Global (alongside Telesign and Route Mobile). Its developer portal at [developer.bics.com](https://developer.bics.com/portal/apis) exposes OAuth2-secured REST APIs at `https://api.bics.com` for A2P SMS and OTP delivery, global number provisioning and portability (MyNumbers), call detail records, emergency services, and carrier-grade cloud connectivity. BICS also offers mobile identity capabilities — phone number verification, HLR/reachability lookup, SIM-swap detection, and device-location signals for anti-fraud and KYC — as partner and carrier contract products across the Proximus Global network rather than as self-serve endpoints.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/bics-network/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/bics-network/refs/heads/main/apis.yml)

## Access model (read this first)

BICS's developer portal is **not fully self-serve**. To use an API you register to consume it on the portal, BICS approves the consumption request (confirmed by email), and the emailed instructions explain how to generate an **OAuth2 token** that you then send as a `Bearer` credential on every request. A **sandbox** environment (`https://sandbox.api.bics.com`) is published for the MyNumbers family for pre-production testing.

The eight portal APIs below are **confirmed** from live OpenAPI 3.0.1 definitions (saved under `openapi/`). Their endpoints and base URLs are real.

The **Number Verification** and **Fraud Prevention / Reachability** entries are **`endpointsModeled`**: BICS markets these mobile-identity and anti-fraud capabilities (number verification, HLR/reachability lookup, SIM-swap detection, device-location signals — aligned with GSMA Open Gateway / CAMARA network APIs) and delivers them as **contact-sales carrier contract products across Proximus Global**, not as self-serve endpoints. No public OpenAPI surface is published for them, so no request definitions are fabricated here.

## Tags

- Number Verification
- Telecom
- Mobile Identity
- Anti-Fraud
- Device Location
- OTP
- SMS
- Numbering
- Number Portability
- Fraud Prevention
- Carrier
- CPaaS

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### BICS SMS API (confirmed)

RESTful A2P messaging for sending text messages worldwide, including one-time passcodes (OTP) for **phone number verification** and two-factor authentication. Single and bulk outbound requests, delivery-info retrieval, inbound message subscriptions, and conversion reporting.

- **Human URL:** [https://developer.bics.com/portal/apis](https://developer.bics.com/portal/apis)
- **Base URL:** `https://api.bics.com/sms/v3`
- [OpenAPI](openapi/bics-sms-openapi.json)

### BICS MyNumbers API (confirmed)

Order and manage ready-to-use BICS Cloud Numbers (IBN), International Freephone Numbers (ITFS), and Global Mobile Numbers (GMN) — stock, price lists, reference data, single/bulk orders, and routes.

- **Human URL:** [https://developer.bics.com/portal/apis](https://developer.bics.com/portal/apis)
- **Base URL:** `https://api.bics.com/mynumbers-number/v1` (sandbox: `https://sandbox.api.bics.com/mynumbers-number/v1`)
- [OpenAPI](openapi/bics-mynumbers-openapi.json)

### BICS MyNumbers Number Porting API (confirmed)

Submit and track **number portability** requests — create requests, attach Letter of Authorization documents, update addresses, and check specifications and statuses.

- **Human URL:** [https://developer.bics.com/portal/apis](https://developer.bics.com/portal/apis)
- **Base URL:** `https://api.bics.com/mynumbers-porting/v1`
- [OpenAPI](openapi/bics-mynumbers-porting-openapi.json)

### BICS MyNumbers CDR API (confirmed)

Request, poll, and download Call Detail Records (CDRs) for inbound and outbound calls, with available-date discovery and multiple download formats.

- **Human URL:** [https://developer.bics.com/portal/apis](https://developer.bics.com/portal/apis)
- **Base URL:** `https://api.bics.com/mynumbers-cdr/v1`
- [OpenAPI](openapi/bics-mynumbers-cdr-openapi.json)

### BICS MyNumbers Address Management API (confirmed)

Create, edit, retrieve, and delete the addresses and supporting documents required by local regulation for number provisioning.

- **Human URL:** [https://developer.bics.com/portal/apis](https://developer.bics.com/portal/apis)
- **Base URL:** `https://api.bics.com/mynumbers-address-management/v1`
- [OpenAPI](openapi/bics-mynumbers-address-management-openapi.json)

### BICS MyNumbers Disconnection API (confirmed)

Request disconnection of your numbers by building disconnection orders, adding or removing order items, and submitting them.

- **Human URL:** [https://developer.bics.com/portal/apis](https://developer.bics.com/portal/apis)
- **Base URL:** `https://api.bics.com/mynumbers-disconnection/v1`
- [OpenAPI](openapi/bics-mynumbers-disconnection-openapi.json)

### BICS MyNumbers Emergency Services API (confirmed)

Enable emergency services on SIP-T numbers — check per-country requirements and create, update, and submit emergency-service orders.

- **Human URL:** [https://developer.bics.com/portal/apis](https://developer.bics.com/portal/apis)
- **Base URL:** `https://api.bics.com/mynumbers-emergency-services/v1`
- [OpenAPI](openapi/bics-mynumbers-emergency-services-openapi.json)

### BICS Connect API (confirmed)

Carrier-grade Cloud Connect service combining BICS layer-2 transport with dedicated cloud connectivity — create, list, modify, and delete connections and interconnects.

- **Human URL:** [https://developer.bics.com/portal/apis](https://developer.bics.com/portal/apis)
- **Base URL:** `https://api.bics.com/connect/v1`
- [OpenAPI](openapi/bics-connect-openapi.json)

### BICS Number Verification API (endpointsModeled — contact sales)

Phone number verification and mobile authentication for **anti-fraud, KYC, and onboarding** — validating that a mobile number is real, active, and controlled by the user, including OTP-based flows. Marketed by BICS and delivered across Proximus Global as a partner/carrier contract product; access is contact-sales, not self-serve, so no OpenAPI surface is published.

- **Human URL:** [https://www.bics.com/developers-hub/](https://www.bics.com/developers-hub/)

### BICS Fraud Prevention and Reachability API (endpointsModeled — contact sales)

Network-signal services for fraud prevention and mobile identity — **HLR / reachability lookup** (operator, ported status, active/blocked SIM state), **SIM-swap detection**, and **device-location** signals used to score login and transaction risk. Offered as carrier contract products across Proximus Global and aligned with GSMA Open Gateway / CAMARA network APIs; contact-sales, not self-serve.

- **Human URL:** [https://www.bics.com/developers-hub/](https://www.bics.com/developers-hub/)

## Common Properties

- [Authentication](authentication/bics-network-authentication.yml)
- [LinkedIn](https://www.linkedin.com/company/bics)
- [Website](https://www.bics.com/)
- [Documentation](https://developer.bics.com/portal/apis)
- [Plans](plans/bics-network-plans-pricing.yml)
- [Rate Limits](rate-limits/bics-network-rate-limits.yml)
- [Fin Ops](finops/bics-network-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
