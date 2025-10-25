---
description: >-
  Use these APIs to automate analytics, SEO reports, and smart links across the
  myGO ecosystem.
icon: terminal
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
  metadata:
    visible: true
---

# Developer Platform API

#### Authentication

All endpoints use **Bearer tokens** via the `Authorization` header.

```
Authorization: Bearer {api_key}
Accept: application/json
Content-Type: application/x-www-form-urlencoded   # for POST/PUT/PATCH with form bodies
```

> #### Get your API key from each product’s dashboard:
>
> * **Analytics:** stats.mygo.ge → Profile → API
> * **Linkers:** linkers.dev → Account → API
> * **mySEO:** myseo.dev → Account → API

***

#### Environments & Base URLs

| Product   | Base URL                       |
| --------- | ------------------------------ |
| Analytics | `https://stats.mygo.ge/api/v1` |
| Linkers   | `https://linkers.dev/api/v1`   |
| mySEO     | `https://myseo.dev/api/v1`     |

***

#### Pagination, Sorting, Filtering

Most list endpoints support:

* `per_page` in `{10,25,50,100}` (default `10`)
* `sort_by` and `sort` (default `sort=desc`)
* Optional `search` and `search_by` fields

#### Errors (common)

* `401 Unauthorized` — missing/invalid token
* `403 Forbidden` — token lacks permission
* `404 Not Found` — resource doesn’t exist
* `422 Unprocessable Entity` — parameter validation failed
* `429 Too Many Requests` — slow down and retry with backoff

***

### Usage tips

* **Date ranges:** Use `from`/`to` in `Y-m-d`. For rolling windows, compute on the client.
* **Rate limits:** If you receive `429`, implement exponential backoff (e.g., 1s, 2s, 4s …).
* **Security:** Prefer **API keys** with least-privilege scopes. Rotate keys regularly.
* **Idempotency:** For create/update calls, you may safely **retry** on network errors; the server validates duplicates by primary keys/aliases where applicable.
* **GDPR/Privacy:** When exporting analytics, ensure downstream systems respect consent and retention policies.

***

### Quick test (copy–paste)

```bash
# 1) Verify account on Analytics
curl -s 'https://stats.mygo.ge/api/v1/account' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {api_key}'

# 2) List Linkers spaces
curl -s 'https://linkers.dev/api/v1/spaces?per_page=25' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {api_key}'

# 3) Create mySEO report
curl -s -X POST 'https://myseo.dev/api/v1/reports' \
  -H 'Authorization: Bearer {api_key}' \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  --data-urlencode 'url=https://example.com/'
```
