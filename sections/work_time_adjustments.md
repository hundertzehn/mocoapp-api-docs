---
layout: default
parent: Users
grand_parent: Entities
---

# User Work Time Adjustments

German: "Korrekturen Zeiterfassung"

- TOC
{:toc}

## Attributes

Work time adjustments contain among the standard fields also:

- User
- Creator

```json
{
  "id": 1972,
  "date": "2022-01-01",
  "description": "Overtime from 2021",
  "hours": 172.01,
  "creator": {
    "id": 933590697,
    "firstname": "Jane",
    "lastname": "Doe"
  },
  "user": {
    "id": 933590696,
    "firstname": "John",
    "lastname": "Doe"
  },
  "created_at": "2022-01-02T17:31:00Z",
  "updated_at": "2022-01-02T17:31:00Z"
}
```

## GET /users/work_time_adjustments

Retrieve all work time adjustments:

```bash
curl -X GET \
  'https://{domain}.mocoapp.com/api/v1/users/work_time_adjustments?from=2018-06-01&to=2018-06-30&user_id=933590696' \
  -H 'Authorization: Token token=YOUR_API_KEY'
```

This returns an array of all work time adjustments.

The following parameters can be supplied:

- [Global filters apply](../entities#global-filters)
- **from** – "2022-01-01"
- **to** – "2022-01-31"
- **user_id** – 123

## GET /users/work_time_adjustments/{id}

Retrieve a single work time adjustment:

```bash
curl -X GET \
  'https://{domain}.mocoapp.com/api/v1/users/work_time_adjustments/{id}' \
  -H 'Authorization: Token token=YOUR_API_KEY'
```

## POST /users/work_time_adjustments

Create a work time adjustment:

```bash
curl -X POST \
  'https://{domain}.mocoapp.com/api/v1/users/work_time_adjustments' \
  -H 'Authorization: Token token=YOUR_API_KEY'
  -H 'Content-Type: application/json' \
  -d '{
        "user_id": 123,
        "description": "Overtime 2021",
        "date": "2022-01-01",
        "hours": 42.0
      }'
```

Mandatory fields are marked with a star (\*):

- **user_id\*** – 123 (user ID)
- **description\*** – a short explanation
- **date\*** - 2022-01-01
- **hours\*** - 42.0 (the amount of hours that should be added or subtracted)

## PUT /users/work_time_adjustments/{id}

Update a work time adjustment:

```bash
curl -X PUT \
  'https://{domain}.mocoapp.com/api/v1/users/work_time_adjustments/{id}' \
  -H 'Authorization: Token token=YOUR_API_KEY'
  -H 'Content-Type: application/json' \
  -d '{
        "description": "A new description"
      }'
```

## DELETE /users/work_time_adjustments/{id}

Delete a work time adjustment:

```bash
curl -X DELETE \
  'https://{domain}.mocoapp.com/api/v1/users/work_time_adjustments/{id}' \
  -H 'Authorization: Token token=YOUR_API_KEY'
```