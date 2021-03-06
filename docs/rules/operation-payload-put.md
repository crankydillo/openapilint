# enforce the `PUT` request payload matches the `GET` `200` response (operation-payload-put)

Validates that the the `PUT` request payload matches the `GET` `200` response.

## Examples of *correct* request/responses

```json
{
  "paths": {
    "/pets": {
      "get": {
        "responses": {
          "200": {
            "description": "sample response",
            "schema": {
              "type": "array",
              "items": {
                "$ref": "#/definitions/pet"
              }
            }
          }
        }
      },
      "put": {
        "parameters": [
          {
            "name": "limit",
            "description": "Sample param description",
            "in": "body",
            "schema": {
              "type": "array",
              "items": {
                "$ref": "#/definitions/pet"
              }
            }
          }
        ]
      }
    }
  }
}
```

## Examples of **incorrect** request/responses


```json
{
  "paths": {
    "/pets": {
      "get": {
        "responses": {
          "200": {
            "description": "sample response",
            "schema": {
              "type": "array",
              "items": {
                "$ref": "#/definitions/pet"
              }
            }
          }
        }
      },
      "put": {
        "parameters": [
          {
            "name": "limit",
            "description": "Sample param description",
            "in": "body",
            "schema": {
              "type": "array",
              "items": {
                "$ref": "#/definitions/alligator"
              }
            }
          }
        ]
      }
    }
  }
}
```
