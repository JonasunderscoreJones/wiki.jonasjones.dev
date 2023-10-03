# Mod Configuartion
---


# betterconsolemc-config.properties
This config file features the overall mod configs
### bettercmd.enable
- This setting, which is true by default, enables or disables the mod

# betterconsolemc-commands_config.properties
This config file features the ingame command configuration
### Syntax
- Command Mode
  - `SIMPLE`: the command will just be ran
  - `RETURN`: the command will be ran and the input will be returned and sent in chat
- Permission Level
   - `1` -`4`, indicates what permission is required to run the command
- Execute Timeout
   - `0`: the command can run forever and will not be terminated at any point - stopping the server will terminate the process
   - `>0`: the command will be terminated after the given amount of seconds
- Broadcast to OP
   - `true`: server operators will be notified that the command was ran by a user and can see who ran it
   - `false`: server operators will not be notified; the action will still appear in the server logs
- Ingame command name
   - The name of the ingame command
- Command to execute
   - (In double quotes) the command that will be ran on the system

Combined, this will give the following one-liner:

`[Command Mode] [Permissione Level] [Execution Timeout] [Broadcast to OP] [Ingame Command name] [command to execute]`

### NOTICE: In version 0.0.1+alpha04 and below, there was an unused ExecutionBlockTimeout property. To update to newer versions, migrate the config file by removing the last number before the `true`/`false`.

### Examples
1. Update the system packages (linux):
   `SIMPLE 4 0 true update "sudo apt update && sudo apt upgrade --force-yes"`
   This creates a command `/update` that automatically updates a debian based linux system. The command is only available to operators, will, at no point, be terminated and can therefore finish without any errors. This aproach requires the server to be ran with elevated permissions (sudo)

2. launch a second minecraft server (linux):
   `SIMPLE 1 300 true start-server "sudo systemctl start minecraft-server.service"`
   This creates a command `/start-server` that automatically starts a minecraft server using the `systemctl` utility. This requires a setup of the service file in `/etc/systemd/system/`

There can only be a single command per line.
