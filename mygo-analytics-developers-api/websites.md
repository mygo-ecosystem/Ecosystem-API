# Websites

### List

**API endpoint:**

GET

```
https://stats.mygo.ge/api/v1/websites
```

Request example:

```
curl --location --request GET 'https://stats.mygo.ge/api/v1/websites' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter   | Type             | Description                                                                                       |
| ----------- | ---------------- | ------------------------------------------------------------------------------------------------- |
| `search`    | optional string  | Search query.                                                                                     |
| `search_by` | optional string  | Search by. Possible values: `domain` for Domain. **Defaults to:** `domain`.                       |
| `favorite`  | optional boolean | Filter by favorite.                                                                               |
| `sort_by`   | optional string  | Sort by. Possible values: `id` for Date created, `domain` for Domain. **Defaults to:** `id`.      |
| `sort`      | optional string  | Sort order. Possible values: `desc` for Descending, `asc` for Ascending. **Defaults to:** `desc`. |
| `per_page`  | optional integer | Results per page. Possible values: `10`, `25`, `50`, `100`. **Defaults to:** `10`.                |

***

### Show

**API endpoint:**

GET

```
https://stats.mygo.ge/api/v1/websites/{id}
```

Request example:

```
curl --location --request GET 'https://stats.mygo.ge/api/v1/websites/{id}' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

***

### Store

**API endpoint:**

POST

```
https://stats.mygo.ge/api/v1/websites
```

Request example:

```
curl --location --request POST 'https://stats.mygo.ge/api/v1/websites' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer {api_key}' \
--data-urlencode 'domain={domain}'
```

| Parameter        | Type             | Description                                                                                                       |
| ---------------- | ---------------- | ----------------------------------------------------------------------------------------------------------------- |
| `domain`         | required string  | Domain name.                                                                                                      |
| `privacy`        | optional integer | Privacy. Possible values: `0` for Public, `1` for Private, `2` for Password. **Defaults to:** `0`.                |
| `password`       | optional string  | Password. Only works when `privacy` is set to `2`.                                                                |
| `email`          | optional integer | Periodic email reports. Possible values: `0` for Disabled, `1` for Enabled. **Defaults to:** `0`.                 |
| `exclude_bots`   | optional integer | Exclude common bots from being tracked. Possible values: `0` for Disabled, `1` for Enabled. **Defaults to:** `1`. |
| `exclude_params` | optional string  | Exclude URL query parameters from tracking (one per line).                                                        |
| `exclude_ips`    | optional string  | Exclude IPs from tracking (one per line).                                                                         |

***

### Update

**API endpoint:**

PUTPATCH

```
https://stats.mygo.ge/api/v1/websites/{id}
```

Request example:

```
curl --location --request PUT 'https://stats.mygo.ge/api/v1/websites/{id}' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter        | Type             | Description                                                                                 |
| ---------------- | ---------------- | ------------------------------------------------------------------------------------------- |
| `privacy`        | optional integer | Privacy. Possible values: `0` for Public, `1` for Private, `2` for Password.                |
| `password`       | optional string  | Password. Only works when `privacy` is set to `2`.                                          |
| `email`          | optional integer | Periodic email reports. Possible values: `0` for Disabled, `1` for Enabled.                 |
| `exclude_bots`   | optional integer | Exclude common bots from being tracked. Possible values: `0` for Disabled, `1` for Enabled. |
| `exclude_params` | optional string  | Exclude URL query parameters from being tracked (one per line).                             |
| `exclude_ips`    | optional string  | Exclude IPs from being tracked (one per line).                                              |
| `favorite`       | optional boolean | Mark website as favorite.                                                                   |

***

### Delete

**API endpoint:**

DELETE

```
https://stats.mygo.ge/api/v1/websites/{id}
```

Request example:

```
curl --location --request DELETE 'https://stats.mygo.ge/api/v1/websites/{id}' \
--header 'Authorization: Bearer {api_key}'
```
