# WhitelistSyncRewrite
Server Side Mod to sync all of your forge server whitelists to a single database, for Minecraft 1.10.2 and up.

Currently supports SQLite and MySQL.

## Use Case
Are you a server owner who is sick of adding individual players to each of your 100 forge servers? Wait you only have 2 forge servers? Well this mod can help you still!

## Download
https://minecraft.curseforge.com/projects/whitelist-sync

## Installation:
### Dependencies
- [json-simple-1.1.1.jar](https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/json-simple/json-simple-1.1.1.jar)
- [sqlite-jdbc-3.19.3.jar](https://bitbucket.org/xerial/sqlite-jdbc/downloads/sqlite-jdbc-3.19.3.jar)
- [mysql-connector-java-8.0.8-dmr](http://central.maven.org/maven2/mysql/mysql-connector-java/8.0.8-dmr/mysql-connector-java-8.0.8-dmr.jar)

Add these to your mods first, so you don't forget.

### The main mod
Now add this mod.

### Configuration
Start your server to generate the config file `whitelistsync.cfg`, then edit it to your needs.


SQLite: Make sure the database path is the same for all servers you want them to link together!

MySQL: Server Address and Authentification are required. The mod makes it's own database!


When the (first) server starts with a new configuraton, it creates a new DB. Use `/wl copyWhiteListToDatabase` sync your existing whitelist to the DB. All other servers can `/wl sync` to get the whitelist. 

## Commands
- `/wl add <player>` | Adds a specified player to whitelist. (Use this instead of /whitelist add)
- `/wl remove <player>` | Removes a specified player from the whitelist. (Use this instead of /whitelist remove)
- `/wl sync` | Pulls whitelist from the database and updates the server whitelist.
- `/wl reloadConfig` | Reloads the config, but a server restart is encouraged.
- `/wl copyServerToDatabase` | Pushes local server whitelist to the database.

