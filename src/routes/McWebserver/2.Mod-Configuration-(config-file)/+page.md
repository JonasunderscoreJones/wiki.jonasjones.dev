# Mod Configuration (config-file)
---
The config file consists of the following entries:
### web.isEnabled
- enables/disables the entire mod
- accepts: `true`/`false`

### web.port
- sets the webserver port
- accepts: `1`...`65535` (make sure to not have port conflicts)

### web.root
- sets the root directory of the webserver, starting from the minecraft server directory
- accepts: any file path

### web.api
- enables/disables the basic API
- accepts: `true`/`false`

### web.api.adv
- enables/disables the advanced API
- accepts: `true`/`false`

### web.file.root
- the name of the html file of the homepage
- accepts: any path with `[filename].html` at the end

### web.file.404
- the name of the 404 page html file
- accepts: any path with `[filename].html` at the end

### web.file.notSupported
- the name of the html file for the "not supported" page if any internal errors occur
- accepts: any path with `[filename].html` at the end

### logger.verbose
- enables/disables the verbose logger (more info at [5. Loggers](/McWebserver/5.Loggers))
- accepts: `true`/`false`