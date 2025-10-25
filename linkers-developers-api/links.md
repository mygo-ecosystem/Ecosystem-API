# Links

### List

**API endpoint:**

GET

```
https://linkers.dev/api/v1/links
```

Request example:

```
curl --location --request GET 'https://linkers.dev/api/v1/links' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter   | Type             | Description                                                                                                                                       |
| ----------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `search`    | optional string  | The search query.                                                                                                                                 |
| `search_by` | optional string  | Search by. Possible values: `title` for Title, `alias` for Alias, `url` for URL. **Defaults to:** `title`.                                        |
| `status`    | optional integer | Filter by status. Possible values: `0` for All, `1` for Active, `2` for Expired, `3` for Disabled. **Defaults to:** `0`.                          |
| `space_id`  | optional integer | Filter by space ID.                                                                                                                               |
| `domain_id` | optional integer | Filter by domain ID.                                                                                                                              |
| `pixel_id`  | optional integer | Filter by pixel ID.                                                                                                                               |
| `sort_by`   | optional string  | Sort by. Possible values: `id` for Date created, `clicks` for Clicks, `title` for Title, `alias` for Alias, `url` for URL. **Defaults to:** `id`. |
| `sort`      | optional string  | Sort order. Possible values: `desc` for Descending, `asc` for Ascending. **Defaults to:** `desc`.                                                 |
| `per_page`  | optional integer | Results per page. Possible values: `10`, `25`, `50`, `100`. **Defaults to:** `10`.                                                                |

***

### Show

**API endpoint:**

GET

```
https://linkers.dev/api/v1/links/{id}
```

Request example:

```
curl --location --request GET 'https://linkers.dev/api/v1/links/{id}' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

***

### Store

**API endpoint:**

POST

```
https://linkers.dev/api/v1/links
```

Request example:

```
curl --location --request POST 'https://linkers.dev/api/v1/links' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer {api_key}' \
--data-urlencode 'url={url}' \
--data-urlencode 'domain={id}'
```

| Parameter                | Type             | Description                                                                                                                         |
| ------------------------ | ---------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `url`                    | required string  | The link to be shortened.                                                                                                           |
| `domain_id`              | required integer | The domain ID the link will be saved under.                                                                                         |
| `alias`                  | optional string  | The link alias.                                                                                                                     |
| `password`               | optional string  | The link password.                                                                                                                  |
| `space_id`               | optional integer | The space ID the link will be saved under.                                                                                          |
| `pixel_ids[]`            | optional array   | The pixel IDs to be integrated in the link.                                                                                         |
| `disabled`               | optional integer | Whether the link is disabled or not. Possible values: `0` for Active, `1` for Disabled. **Defaults to:** `0`.                       |
| `privacy`                | optional integer | Whether the link stats are public or not. Possible values: `0` for Public, `1` for Private, `2` for Password. **Defaults to:** `0`. |
| `privacy_password`       | optional string  | The password for the statistics page. Only works when `privacy` is set to `2`.                                                      |
| `expiration_url`         | optional string  | The URL to redirect users to after the link has expired.                                                                            |
| `expiration_date`        | optional string  | The link expiration date in `YYYY-MM-DD` format.                                                                                    |
| `expiration_time`        | optional string  | The link expiration time in `HH:MM` format.                                                                                         |
| `expiration_clicks`      | optional integer | The number of clicks after which the link should expire.                                                                            |
| `target_type`            | optional integer | The type of targeting. Possible values: `0` for None, `1` for Geographic, `2` for Platform, `4` for Rotation.                       |
| `country[index][key]`    | optional string  | Targeted country code in **ISO 3166-1 alpha-2** format.                                                                             |
| `country[index][value]`  | optional string  | The URL to redirect the targeted country to.                                                                                        |
| `platform[index][key]`   | optional string  | Targeted platform. Possible values: `iOS`, `Android`, `Windows`, `OS X`, `Linux`, `Ubuntu`, `Chrome OS`.                            |
| `platform[index][value]` | optional string  | The URL to redirect the targeted platform to.                                                                                       |
| `language[index][key]`   | optional string  | Targeted language code in **ISO 639-1 alpha-2** format.                                                                             |
| `language[index][value]` | optional string  | The URL to redirect the targeted language to.                                                                                       |
| `rotation[index][value]` | optional string  | The URL used for rotation targeting.                                                                                                |

***

### Update

**API endpoint:**

PUTPATCH

```
https://linkers.dev/api/v1/links/{id}
```

Request example:

```
curl --location --request PUT 'https://linkers.dev/api/v1/links/{id}' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer {api_key}' \
--data-urlencode 'url={url}'
```

| Parameter                | Type             | Description                                                                                                   |
| ------------------------ | ---------------- | ------------------------------------------------------------------------------------------------------------- |
| `url`                    | optional string  | The link to be shortened.                                                                                     |
| `alias`                  | optional string  | The link alias.                                                                                               |
| `password`               | optional string  | The link password.                                                                                            |
| `space_id`               | optional integer | The space ID the link will be saved under.                                                                    |
| `pixel_ids`              | optional array   | The pixel IDs to be integrated in the link.                                                                   |
| `disabled`               | optional integer | Whether the link is disabled or not. Possible values: `0` for Active, `1` for Disabled.                       |
| `privacy`                | optional integer | Whether the link stats are public or not. Possible values: `0` for Public, `1` for Private, `2` for Password. |
| `privacy_password`       | optional string  | The password for the statistics page. Only works when `privacy` is set to `2`.                                |
| `expiration_url`         | optional string  | The URL to redirect users to after the link has expired.                                                      |
| `expiration_date`        | optional string  | The link expiration date in `YYYY-MM-DD` format.                                                              |
| `expiration_time`        | optional string  | The link expiration time in `HH:MM` format.                                                                   |
| `expiration_clicks`      | optional integer | The number of clicks after which the link should expire.                                                      |
| `target_type`            | optional integer | The type of targeting. Possible values: `0` for None, `1` for Geographic, `2` for Platform, `4` for Rotation. |
| `country[index][key]`    | optional string  | Targeted country code in **ISO 3166-1 alpha-2** format.                                                       |
| `country[index][value]`  | optional string  | The URL to redirect the targeted country to.                                                                  |
| `platform[index][key]`   | optional string  | Targeted platform. Possible values: `iOS`, `Android`, `Windows`, `OS X`, `Linux`, `Ubuntu`, `Chrome OS`.      |
| `platform[index][value]` | optional string  | The URL to redirect the targeted platform to.                                                                 |
| `language[index][key]`   | optional string  | Targeted language code in **ISO 639-1 alpha-2** format.                                                       |
| `language[index][value]` | optional string  | The URL to redirect the targeted language to.                                                                 |
| `rotation[index][value]` | optional string  | The URL used for rotation targeting.                                                                          |

***

### Delete

**API endpoint:**

DELETE

```
https://linkers.dev/api/v1/links/{id}
```

Request example:

```
curl --location --request DELETE 'https://linkers.dev/api/v1/links/{id}' \
--header 'Authorization: Bearer {api_key}'
```
