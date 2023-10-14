# Errors
---
When interacting with the API some errors can occur.

## Bad Request
- Occurs when a request doesn't exist
```
http://localhost:8080/api/v1/getmotd
```
In this example the request is wrong. `getmotd` isn't a valid request.
- Response
```json
{
  "error": {
    "status": 400,
    "message": "Bad Request"
  }
}
```

## Internal Server Error
- Occurs when something unexpected happens internally while handling the request. This most likely has nothing to do with you.

One possible way of getting the error message is to send the request before the server has fully started, e.g. while it's still loading the world.

- Response
```json
{
  "error": {
    "status": 500,
    "message": "Internal Server Error"
  }
}
```