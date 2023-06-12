# Admin Commands

This page lists up all administrator commands.

### `/tpo`

**Usage:** /tpo \<Player Name>\
**Description:** Teleports yourself to a specified player.\
**Permission:** at.admin.tpo\
**Arguments:**

* `<Player Name>` - The name of the player you want to teleport to. If they are not online, the command will not run.

### `/tpohere`

**Usage:** /tpohere \<Player Name>\
**Description:** Teleports a player to you.\
**Permission:** at.admin.tpohere\
**Arguments:**

* `<Player Name>` - The name of the player to be teleported to you. If they are not online, the command will not run.

### `/tpaall`

**Usage:** /tpaall\
**Description:** Sends a teleport request to everyone online, which teleports the player to you when accepted, acting similar to /tpahere.\
**Permission:** at.admin.all

### `/setspawn`

**Usage:** /setspawn\
**Description:** Sets the spawnpoint of your server at your location.\
**Permission:** at.admin.setspawn

### `/setwarp`

**Usage:** /setwarp \<Warp Name>\
**Description:** Sets a warp with a specified name at your location.\
**Permission:** at.admin.setwarp\
**Arguments:**

* `<Warp Name>` - The name to be used for the warp. This will be used in the /warp command when a player wants to teleport to the warp.

### `/delwarp`

**Usage:** /delwarp \<Warp Name>\
**Description:** Deletes a warp with the specified name.\
**Permission:** at.admin.delwarp\
**Arguments:**

* `<Warp Name>` - The name of the warp to be deleted.

### `/movewarp`

**Usage:** /movewarp \<Warp Name>\
**Description:** Moves the warp with the specified name.\
**Permission:** at.admin.movewarp\
**Arguments:**

* `<Warp Name>` - The name of the warp to be moved.

### `/tpoffline`

**Usage:** /tpoffline \<Player Name>\
**Description:** Teleports to a player's location. If they are online, the command will operate as /tpo instead with all permission checks. Otherwise, their last known location is used.\
**Permission:** at.admin.tpoffline\
**Aliases:** /tpoffl\
**Arguments:**

* `<Player Name>` - The name of the player to be teleported to.

### `/tpofflinehere`

**Usage:** /tpofflinehere \<Player Name>\
**Description:** Teleports a player to your location. If they are online, the command will operate as /tpohere instead with all permission checks. Otherwise, their login location is updated.\
**Permission:** at.admin.tpofflinehere\
**Aliases:** /tpofflh, /tpofflhere\
**Arguments:**

* `<Player Name>` - The name of the player to be teleported.

### `/tploc`

**Usage:** /tploc \<X> \<Y> \<Z> \[Yaw] \[Pitch] \[World] \[Player] \[noflight|precise]\
**Description:** Teleports you or another player to a specific location.\
**Permission:** at.admin.tploc\
**Arguments:**

* `<X>` - The X coordinate you are to be teleported to, you can use \~ to represent your current X coordinate.
* `<Y>` - The Y coordinate you are to be teleported to, you can use \~ to represent your current Y coordinate.
* `<Z>` - The Z coordinate you are to be teleported to, you can use \~ to represent your current Z coordinate.
* `[Yaw]` - The yaw at which your head will be at when teleported (looking left/right), you can use \~ to represent your current yaw.
* `[Pitch]` - The pitch at which your head will be at when teleported (looking up/down), you can use \~ to represent your current pitch.
* `[World]` - The world at which you will be teleported to, you can use \~ to represent your current world.
* `[Player]` - The player to be teleported. Requires the `at.admin.tploc.others` permission.
* `[noflight|precise]` - Two options which specify how you end up teleported. `noflight` means your flight is turned off and you are left to fall freely. `precise` means you will be flying and `at.admin.tploc.safe-teleport` is required for this.

### `/setspawn`

**Usage:** /setspawn \[ID]\
**Description:** Sets a spawn either for the specified world or a given ID. If no spawnpoint used within the plugin has been set previously, this will be made the main spawnpoint.\
**Permission:** at.admin.setspawn\
**Arguments:**

* `[ID]` - The ID of the spawn to be used when creating this spawnpoint.

### `/mirrorspawn`

**Usage:** /mirrorspawn \<To Spawn>|\[From World] \[To Spawn]\
**Description:** Mirrors the /spawn location of a world to another spawnpoint of a given ID.\
**Permission:** at.admin.mirrorspawn\
**Arguments:**

* `<To Spawn>` - The ID of the spawnpoint that the world you're currently in will redirect to when /spawn is used in that world.
* `[From World]` - The name of the world that will have its spawn mirrored to a different point. Must have a `To Spawn` argument following it.

### `/setmainspawn`

**Usage:** /setmainspawn \[ID]\
**Description:** Sets the main spawn in the plugin, so that if /spawn is used in a world with no redirects, it will teleport to this spawn.\
**Permission:** at.admin.setmainspawn\
**Arguments:**

* `[ID]` - The ID of the spawnpoint that will be used for the main spawnpoint. If the spawnpoint with the ID does not exist, it is created as long as the user has `at.member.setspawn` or `at.member.setspawn.other` if setting in a different world.

### `/removespawn`

**Usage:** /removespawn \[ID]\
**Description:** Removes the spawn of a given ID.\
**Permission:** at.admin.removespawn\
**Arguments:**

* `[ID]` - The ID of the spawnpoint that will be removed.

### `/at clearcache`

**Usage:** /at clearcache\
**Description:** Clears the RTP cache within the plugin.\
**Permission:** at.admin.core.clearcache

### `/at reload`

**Usage:** /at reload\
**Description:** Reloads all configuration within the plugin.\
**Permission:** at.admin.core.reload

### `/at import`

**Usage:** /at import \<Plugin> \[Data]\
**Description:** Imports data from a specified plugin into AT's data storage.\
**Permission:** at.admin.core.import\
**Arguments:**

* `<Plugin>` - The plugin to have its data imported. Currently, this can only be Essentials.
* `[Data]` - The type of data to be imported. Valid options include `Homes`, `Warps`, `Spawns`, `lastlocs`, `Players`. Any other specified option imports all data.

### `/at export`

**Usage:** /at export \<Plugin> \[Data]\
**Description:** Exports data from AT's data storage into another plugin's storage.\
**Permission:** at.admin.core.export\
**Arguments:**

* `<Plugin>` - The plugin to have its data exported. Currently, this can only be Essentials.
* `[Data]` - The type of data to be exported. Valid options include `Homes`, `Warps`, `Spawns`, `lastlocs`, `Players`. Any other specified option exports all data.

### `/at purge`

Usage: /at purge \<warps|homes> \<world|player> \<World Name|Player Name>\
Description: Deletes either warps or homes from a specific world or belonging to a specific player.\
Arguments:

* `<Warps|Homes>` - Either Warps to delete warps, or Homes to delete homes.
* `<World|Player>` - Either World to indicate deleting in a world, or Player to indicate deleting a player's data.
* `<World Name|Player Name>` - The world or player name that is having data attached to it deleted.
