## Server Get All
---
- Returns the Server's entire data of the Simple API
```
http://localhost:8080/api/v1/getall
```
- Response:
```json
{
  "SERVER_IP": "",
  "SERVER_PORT": 25565,
  "SERVER_NAME": "Server",
  "DEFAULT_GAME_MODE": "SURVIVAL",
  "LOADER_VERSION": "0.14.22",
  "METADATA": {
    "DESCRIPTION": "A Minecraft Server",
    "PLAYERS": {
      "MAX": 20,
      "ONLINE": 1,
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
    "SECURE_CHAT_EINFORCED": true
  },
  "TICKS": 29066,
  "TICK_TIME": 4.6665154,
  "TIME_REFERENCE": 29606414
}
```
NOTE: *v0.3.0 returns an additional property* `LEGACY` *for every player that states whether or not the account is a legacy account or not. Since mc 1.20.2 and the mod release 0.3.1 this was removed due to the end of the account migration period, where all legacy accounts were migrated to microsoft accounts. (This property is now always false and thus redundant)*