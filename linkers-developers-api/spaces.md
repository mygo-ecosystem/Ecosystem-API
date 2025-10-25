# Spaces

### List

**API endpoint:**

GET

```
https://linkers.dev/api/v1/spaces
```

Request example:

```
curl --location --request GET 'https://linkers.dev/api/v1/spaces' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter   | Type             | Description                                                                                       |
| ----------- | ---------------- | ------------------------------------------------------------------------------------------------- |
| `search`    | optional string  | The search query.                                                                                 |
| `search_by` | optional string  | Search by. Possible values: `name` for Name. **Defaults to:** `name`.                             |
| `sort_by`   | optional string  | Sort by. Possible values: `id` for Date created, `name` for Name. **Defaults to:** `id`.          |
| `sort`      | optional string  | Sort order. Possible values: `desc` for Descending, `asc` for Ascending. **Defaults to:** `desc`. |
| `per_page`  | optional integer | Results per page. Possible values: `10`, `25`, `50`, `100`. **Defaults to:** `10`.                |

***

### Show

**API endpoint:**

GET

```
https://linkers.dev/api/v1/spaces/{id}
```

Request example:

```
curl --location --request GET 'https://linkers.dev/api/v1/spaces/{id}' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

***

### Store

**API endpoint:**

POST

```
https://linkers.dev/api/v1/spaces
```

Request example:

```
curl --location --request POST 'https://linkers.dev/api/v1/spaces' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer {api_key}' \
--data-urlencode 'name={name}'
```

| Parameter | Type             | Description                                                                          |
| --------- | ---------------- | ------------------------------------------------------------------------------------ |
| `name`    | required string  | The space name.                                                                      |
| `color`   | optional integer | The color code. Possible values: `1`, `2`, `3`, `4`, `5`, `6`. **Defaults to:** `1`. |

***

### Update

**API endpoint:**

PUTPATCH

```
https://linkers.dev/api/v1/spaces/{id}
```

Request example:

```
curl --location --request PUT 'https://linkers.dev/api/v1/spaces/{id}' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter | Type             | Description                                                    |
| --------- | ---------------- | -------------------------------------------------------------- |
| `name`    | optional string  | The space name.                                                |
| `color`   | optional integer | The color code. Possible values: `1`, `2`, `3`, `4`, `5`, `6`. |

***

### Delete

**API endpoint:**

DELETE

```
https://linkers.dev/api/v1/spaces/{id}
```

Request example:

```
curl --location --request DELETE 'https://linkers.dev/api/v1/spaces/{id}' \
--header 'Authorization: Bearer {api_key}'
```
