# Loggers
---
McWebserver has two different loggers: Default and Verbose.

## Default Logger
This loggers is always enabled and logs the most important stuff such as:
- Mod initialized
- Webserver enabled/disabled
- API enabled/disabled
- Webserver starting/stopping
- Webserver started/stopped
- Internal errors while handling requests (this means only error 500)

## Verbose Logger
This logger can be toggled in the config file and logs stuff like:
- Verbose Logger enabled
- Config loaded
- Connection opened/closed
