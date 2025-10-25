# Stats

### Show

**API endpoint:**

GET

```
https://linkers.dev/api/v1/stats/{id}
```

Request example:

```
curl --location --request GET 'https://linkers.dev/api/v1/stats/{id}?name={name}&from={from}&to={to}' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter   | Type             | Description                                                                                                                                        |
| ----------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `name`      | required string  | The name of the statistic. Possible values: `browser`, `cities`, `clicks`, `clicks_hour`, `country`, `device`, `language`, `platform`, `referrer`. |
| `from`      | required string  | The starting date in `Y-m-d` format.                                                                                                               |
| `to`        | required string  | The ending date in `Y-m-d` format.                                                                                                                 |
| `search`    | optional string  | The search query.                                                                                                                                  |
| `search_by` | optional string  | Search by. Possible values: `value` for Value. **Defaults to:** `url`.                                                                             |
| `sort_by`   | optional string  | Sort by. Possible values: `count` for Count, `value` for Value. **Defaults to:** `count`.                                                          |
| `sort`      | optional string  | Sort order. Possible values: `desc` for Descending, `asc` for Ascending. **Defaults to:** `desc`.                                                  |
| `per_page`  | optional integer | Results per page. Possible values: `10`, `25`, `50`, `100`. **Defaults to:** `10`.                                                                 |
