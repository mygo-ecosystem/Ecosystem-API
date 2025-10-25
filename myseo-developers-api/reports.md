# Reports

### List

**API endpoint:**

GET

```
https://myseo.dev/api/v1/reports
```

Request example:

```
curl --location --request GET 'https://myseo.dev/api/v1/reports' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter   | Type             | Description                                                                                                                                    |
| ----------- | ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| `search`    | optional string  | The search query.                                                                                                                              |
| `search_by` | optional string  | Search by. Possible values: `url` for URL. **Defaults to:** `url`.                                                                             |
| `project`   | optional string  | The project name.                                                                                                                              |
| `result`    | optional string  | The report result. Possible values: `good` for Good, `decent` for Decent, `bad` for Bad.                                                       |
| `sort_by`   | optional string  | Sort by. Possible values: `id` for Date created, `generated_at` for Date generated, `url` for URL, `result` for Result. **Defaults to:** `id`. |
| `sort`      | optional string  | Sort order. Possible values: `desc` for Descending, `asc` for Ascending. **Defaults to:** `desc`.                                              |
| `per_page`  | optional integer | Results per page. Possible values: `10`, `25`, `50`, `100`. **Defaults to:** `25`.                                                             |

***

### Show

**API endpoint:**

GET

```
https://myseo.dev/api/v1/reports/{id}
```

Request example:

```
curl --location --request GET 'https://myseo.dev/api/v1/reports/{id}' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

***

### Store

**API endpoint:**

POST

```
https://myseo.dev/api/v1/reports
```

Request example:

```
curl --location --request POST 'https://myseo.dev/api/v1/reports' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer {api_key}' \
--data-urlencode 'url={url}'
```

| Parameter  | Type             | Description                                                                                                    |
| ---------- | ---------------- | -------------------------------------------------------------------------------------------------------------- |
| `url`      | required string  | The webpage’s URL.                                                                                             |
| `privacy`  | optional integer | Report page privacy. Possible values: `0` for Public, `1` for Private, `2` for Password. **Defaults to:** `0`. |
| `password` | optional string  | The password for the report page. Only works when `privacy` is set to `2`.                                     |

***

### Update

**API endpoint:**

PUTPATCH

```
https://myseo.dev/api/v1/reports/{id}
```

Request example:

```
curl --location --request PUT 'https://myseo.dev/api/v1/reports/{id}' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter  | Type             | Description                                                                                |
| ---------- | ---------------- | ------------------------------------------------------------------------------------------ |
| `privacy`  | optional integer | Report page privacy. Possible values: `0` for Public, `1` for Private, `2` for Password.   |
| `password` | optional string  | The password for the report page. Only works when `privacy` is set to `2`.                 |
| `results`  | optional integer | Update the report results. Possible values: `0` for No, `1` for Yes. **Defaults to:** `0`. |

***

### Delete

**API endpoint:**

DELETE

```
https://myseo.dev/api/v1/reports/{id}
```

Request example:

```
curl --location --request DELETE 'https://myseo.dev/api/v1/reports/{id}' \
--header 'Authorization: Bearer {api_key}'
```
