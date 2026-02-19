<!--
This file is the GitHub org profile README.
Put it at: `.github/profile/README.md`
-->

# Fieldkit

**Physical marketing production — we make cool shit**

Fieldkit is a physical marketing agency built by printers, fabricators, designers, and project managers. We help brands bring real-world campaigns to life! We work on everything from small print campaigns to full scale brand build outs.

---

## Quick links

- Marketing: https://www.builtbyfieldkit.com
- Customer Portal: https://fieldkit.cc
- Docs (developers + print prep + guides): https://docs.fieldkit.cc
- Fieldkit Print (self-serve ordering): https://fieldkitprint.com

---

## We like to make stuff

This org contains the software and tooling behind our operational platform including:

- **Public API** + docs tooling (OpenAPI, webhooks)
- **Shared libs** (types/schemas/SDKs)
- **Infra** Shared assets and tools for the print industry
- **Open Graphtec Server** Our open source Graphtec datalink cutting server implementation

We aim to build things that are usable by the wider print industry as well as us

---

## Public API (v1)

Fieldkit exposes a customer/partner **Public API** (currently **Beta**).

### Base URL
Your onboarding provides sandbox + production base URLs. Production is:

- `https://api.fieldkit.cc`

### Base path
All v1 endpoints live under:

- `/public/v1/*`

### Auth
Public API supports:
- API keys: `X-Public-API-Key: <key>`
- OAuth bearer tokens: `Authorization: Bearer <access_token>`

### Important behaviors
- **Idempotency**: write endpoints require `Idempotency-Key: <uuid>`
- **Request IDs**: every response includes `X-Request-Id`; errors include `error.request_id`

### Quickstart (curl)

List products:
```bash
curl -sS \
  -H "X-Public-API-Key: $FIELDKIT_PUBLIC_API_KEY" \
  "https://api.fieldkit.cc/public/v1/products"
