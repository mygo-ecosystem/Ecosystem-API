# Pixels

### List

**API endpoint:**

GET

```
https://linkers.dev/api/v1/pixels
```

Request example:

```
curl --location --request GET 'https://linkers.dev/api/v1/pixels' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter   | Type             | Description                                                                                                                                                   |
| ----------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `search`    | optional string  | The search query.                                                                                                                                             |
| `search_by` | optional string  | Search by. Possible values: `name` for Name. **Defaults to:** `name`.                                                                                         |
| `type`      | optional string  | The pixel type. Possible values: `adroll`, `bing`, `facebook`, `google-ads`, `google-analytics`, `google-tag-manager`, `linkedin`, `pinterest`, `quora`, `x`. |
| `sort_by`   | optional string  | Sort by. Possible values: `id` for Date created, `name` for Name. **Defaults to:** `id`.                                                                      |
| `sort`      | optional string  | Sort order. Possible values: `desc` for Descending, `asc` for Ascending. **Defaults to:** `desc`.                                                             |
| `per_page`  | optional integer | Results per page. Possible values: `10`, `25`, `50`, `100`. **Defaults to:** `10`.                                                                            |

***

### Show

**API endpoint:**

GET

```
https://linkers.dev/api/v1/pixels/{id}
```

Request example:

```
curl --location --request GET 'https://linkers.dev/api/v1/pixels/{id}' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

***

### Store

**API endpoint:**

POST

```
https://linkers.dev/api/v1/pixels
```

Request example:

```
curl --location --request POST 'https://linkers.dev/api/v1/pixels' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer {api_key}' \
--data-urlencode 'name={name}' \
--data-urlencode 'type={type}' \
--data-urlencode 'value={value}'
```

| Parameter | Type            | Description                                                                                                                                                   |
| --------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `name`    | required string | The pixel name.                                                                                                                                               |
| `type`    | required string | The pixel type. Possible values: `adroll`, `bing`, `facebook`, `google-ads`, `google-analytics`, `google-tag-manager`, `linkedin`, `pinterest`, `quora`, `x`. |
| `value`   | required string | The pixel ID value.                                                                                                                                           |

***

### Update

**API endpoint:**

PUTPATCH

```
https://linkers.dev/api/v1/pixels/{id}
```

Request example:

```
curl --location --request PUT 'https://linkers.dev/api/v1/pixels/{id}' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter | Type            | Description                                                                                                                                                   |
| --------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `name`    | optional string | The pixel name.                                                                                                                                               |
| `type`    | optional string | The pixel type. Possible values: `adroll`, `bing`, `facebook`, `google-ads`, `google-analytics`, `google-tag-manager`, `linkedin`, `pinterest`, `quora`, `x`. |
| `value`   | optional string | The pixel ID value.                                                                                                                                           |

***

### Delete

**API endpoint:**

DELETE

```
https://linkers.dev/api/v1/pixels/{id}
```

Request example:

```
curl --location --request DELETE 'https://linkers.dev/api/v1/pixels/{id}' \
--header 'Authorization: Bearer {api_key}'
```
