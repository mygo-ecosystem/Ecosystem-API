# Stats

### Show

**API endpoint:**

GET

```
https://stats.mygo.ge/api/v1/stats/{website_id}
```

Request example:

```
curl --location --request GET 'https://stats.mygo.ge/api/v1/stats/{website_id}?name={name}&from={from}&to={to}' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter   | Type             | Description                                                                                                                                                                                      |
| ----------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `name`      | required string  | Name. Possible values: `browser`, `campaign`, `city`, `continent`, `country`, `device`, `event`, `language`, `operating_system`, `page`, `pageview`, `referrer`, `screen_resolution`, `visitor`. |
| `from`      | required string  | Starting date in `Y-m-d` format.                                                                                                                                                                 |
| `to`        | required string  | Ending date in `Y-m-d` format.                                                                                                                                                                   |
| `search`    | optional string  | Search query.                                                                                                                                                                                    |
| `search_by` | optional string  | Search by. Possible values: `value` for Value.                                                                                                                                                   |
| `sort_by`   | optional string  | Sort by. Possible values: `count` for Count, `value` for Value. **Defaults to:** `count`.                                                                                                        |
| `sort`      | optional string  | Sort order. Possible values: `desc` for Descending, `asc` for Ascending. **Defaults to:** `desc`.                                                                                                |
| `per_page`  | optional integer | Results per page. Possible values: `10`, `25`, `50`, `100`. **Defaults to:** `10`.                                                                                                               |
