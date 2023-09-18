# Web-API
---
*This feature exists as of version 0.3.0 of McWebserver*

The API is split into two parts. the Simple API and the Advanced API.

# What is an API?
An API allows you to get information from the server in form of `json` code.

As an example we can fetch ourselves the server MOTD to display it on our website.

This API call will get you the following response:
- API call (replace `localhost` with your IP and the port with your actual webserver port from the config file):
```
http://localhost:8080/api/v1/motd
```
- Result:
```json
["A Minecraft Server"]
```


# Simple API
This API allows you to gather the most surface-level information about your server.

**All API calls have the prefix `/api/v1/`.**

The supported API calls are

### Server MOTD
- Returns the Server MOTD
```
http://localhost:8080/api/v1/motd
```
- Response:
```json
["A Minecraft Server"]
```

### Server IP  address
- Returns the Server's IP address, if set in the server's `server.properties` file, or else returns an empty string
```
http://localhost:8080/api/v1/serverip
```
- Response:
```json
[""]
```

### Server Port
- Returns the Server's port
```
http://localhost:8080/api/v1/serverport
```
- Response:
```json
["25565"]
```

### Server Name
- Returns the Server's Name, if set in the server's `server.properties` file, or else returns an empty string
```
http://localhost:8080/api/v1/servername
```
- Response:
```json
["Server"]
```

### Server MC Version
- Returns the Server's Minecraft Version
```
http://localhost:8080/api/v1/serverversion
```
- Response:
```json
["1.20.1"]
```

### Fabric/Quilt Loader Version
- Returns the Mod-loader version
```
http://localhost:8080/api/v1/loaderversion
```
- Response:
```json
["0.14.22"]
```

### Server Player Count
- Returns the current player count.
```
http://localhost:8080/api/v1/currentplayercount
```
- Response:
```json
["0"]
```

### Server Default Gamemode
- Returns the Server's default gamemode
```
http://localhost:8080/api/v1/defaultgamemode
```
- Responses:
```json
["SURVIVAL"]
```
or
```json
["CREATIVE"]
```
or
```json
["SPECTATOR"]
```

### Server Max Player Count
- Returns the Server's maximum player allowance
```
http://localhost:8080/api/v1/maxplayercount
```
- Response:
```json
["20"]
```

### Server Current Player Names
- Returns the Server's currently online players
```
http://localhost:8080/api/v1/playernames
```
- Response:
```json
[
  {
    "ID": "c888eef5-edb7-4ceb-bbf3-987731de9747",
    "NAME": "Jonas_Jones",
    "LEGACY": false
  }
]
```

### Server Ticks
- Returns the Server's tick count
```
http://localhost:8080/api/v1/ticks
```
- Response:
```json
["20456"]
```

### Server Ticktime
- Returns the Server's time it takes to process a single tick in Milliseconds
```
http://localhost:8080/api/v1/ticktime
```
- Response:
```json
["0.1235235"]
```

### Server Time-reference
- Returns the Server's in-game time of the day of the overworld
```
http://localhost:8080/api/v1/timereference
```
- Response:
```json
["20"]
```

### Server Metadata
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
      "NAME": "Anonymous Player",
      "LEGACY": false
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

### Server All-Info
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
          "NAME": "Anonymous Player",
          "LEGACY": false
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

### Server Favicon
- Returns the server icon image in form of a png
```
http://localhost:8080/api/v1/favicon
```
- Response
[image/png]

## Errors
When interacting with the API some errors can occur.

### Bad Request
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

### Internal Server Error
- Occurs when something unexpected happens internally while handling the request. This most likely has nothing to do with you.

One possible way of getting the error message is to send the request before the server has fully started, more precise while loading the world.

- Response
```json
{
  "error": {
    "status": 500,
    "message": "Internal Server Error"
  }
}
```
# Advanced API
This is still WIP and is unreleased.
In the future it will be possible to get more information about players, their ingame coordinates, inventory, etc.
Stay tuned for updates!