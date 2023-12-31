## Server Metadata
---
- Returns the Server's Metadata. This includes all the information that is also being sent to a Minecraft client when pinging the server.
```
http://localhost:8080/api/v1/servermetadata
```
- Response:
```json
{
  "DESCRIPTION": "A Minecraft Server",
  "PLAYERS": {
    "MAX":20,
    "ONLINE":1,
    "SAMPLE": [
      {
      "ID": "00000000-0000-0000-0000-000000000000",
      "NAME": "Anonymous Player"
      }
    ]
  },
  "VERSION": {
    "version": "1.20.1",
    "protocol": 763
  },
  "FAVICON": "/api/v1/servericon",
  "SECURE_CHAT_EINFORCED":true
}
```
NOTE: *v0.3.0 returns an additional property* `LEGACY` *for every player that states whether or not the account is a legacy account or not. Since mc 1.20.2 and the mod release 0.3.1 this was removed due to the end of the account migration period, where all legacy accounts were migrated to microsoft accounts. (This property is now always false and thus redundant)*