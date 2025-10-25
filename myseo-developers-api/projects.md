# Projects

### List

**API endpoint:**

GET

```
https://myseo.dev/api/v1/projects
```

Request example:

```
curl --location --request GET 'https://myseo.dev/api/v1/projects' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer {api_key}'
```

| Parameter   | Type             | Description                                                                                                 |
| ----------- | ---------------- | ----------------------------------------------------------------------------------------------------------- |
| `search`    | optional string  | The search query.                                                                                           |
| `search_by` | optional string  | Search by. Possible values: `project` for Name. **Defaults to:** `project`.                                 |
| `sort_by`   | optional string  | Sort by. Possible values: `created_at` for Date created, `project` for Name. **Defaults to:** `created_at`. |
| `sort`      | optional string  | Sort order. Possible values: `desc` for Descending, `asc` for Ascending. **Defaults to:** `desc`.           |
| `per_page`  | optional integer | Results per page. Possible values: `10`, `25`, `50`, `100`. **Defaults to:** `25`.                          |

***

### Delete

**API endpoint:**

DELETE

```
https://myseo.dev/api/v1/projects/{project}
```

Request example:

```
curl --location --request DELETE 'https://myseo.dev/api/v1/projects/{project}' \
--header 'Authorization: Bearer {api_key}'
```
