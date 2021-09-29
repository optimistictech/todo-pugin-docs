# Create a Todo #
This endpoint is used to create a todo
|  |  |
| ------ | ------ |
| Request Type | ``` POST ``` |
| Endpoint |  ``` /create-todo ``` |

Body Params
| Param	 | Required | Description |
| ------ | ------ | ------ |
| organisation_id |  yes | string |
| title |  yes | string |
| user_id |  yes | integer |
| type |  yes | string |

Sample Request
```json

      {
            "organisation_id": "614679ee1a5607b13c00bcb7",
            "title": "check",
            "user_id": "123",
            "type": "todo",
            
      }

```
Sample Response
```json
{
    "status": "success",
    "type": "Todo",
    "data": {
        "_id": "61548df27f0874785c51cb2b",
        "organisation_id": "614679ee1a5607b13c00bcb7",
        "title": "check",
        "user_id": "123",
        "type": "todo",
        "channel": "61548df2d76d-check",
        "tasks": [],
        "labels": [],
        "collaborators": [],
        "created_at": "2021-09-29T16:01:54.882458Z"
    }
}
```

# Fetch all User Todos #
This endpoint is used to fetch all user todo
|  |  |
| ------ | ------ |
| Request Type | ``` GET ``` |
| Endpoint |  ``` /user-todo ``` |

Body Params
| Param	 | Required | Description |
| ------ | ------ | ------ |
| organisation_id |  yes | string |
| user_id |  yes | integer |

Sample Request
```json

      {
            "organisation_id": "614679ee1a5607b13c00bcb7",
            "user_id": "123"
            
      }

```
Sample Response
```json
{
    "status": "success",
    "type": "Todo Collection",
    "count": 6,
    "data": [
        {
            "_id": "61548ae67f0874785c51cb05",
            "channel": "61548ae70ab6-check",
            "collaborators": [],
            "created_at": "2021-09-29T15:48:55.043938Z",
            "labels": [],
            "organisation_id": "614679ee1a5607b13c00bcb7",
            "tasks": [],
            "title": "check",
            "type": "null",
            "user_id": "123"
        }
    ]
}
```

- Invalid request
  - Description: Invalid organisation_id 
    - Status code: 400

Sample Response
```json
{
    "status": 404,
    "message": "collection not found"
}
```
