---
description: >-
  A list of commands that are automatically given to all players in the default
  configuration.
---

# 🔰 Member Commands

This page lists up commands available to all players by default. All of these commands are provided through `at.member.*`.

{% hint style="info" %}
<> indicate mandatory arguments, whilst \[] indicate optional arguments.
{% endhint %}

### `/tpa`

**Usage:** `/tpa <Player Name>`\
**Description:** Sends a teleportation request to another player, asking to teleport to the player's location.\
**Permission:** `at.member.tpa`\
**Arguments:**

* `<Player Name>` - the name of the player to be teleported to.

***

### `/tpahere`

**Usage:** `/tpahere <Player Name>`\
**Description:** Sends a teleportation request to another player, asking the player to teleport to you.\
**Permission:** `at.member.here`\
**Arguments:**

* `<Player Name>` - the name of the player to be teleported to the sender.

***

### `/tpcancel`

**Usage:** `/tpcancel [Player Name]`\
**Description:** Cancels a previously sent teleport request. If there is only one teleport request that has been sent out, then the player name argument is not required.\
**Permission:** `at.member.cancel`\
**Arguments:**

* `[Player Name]` - the name of the player whose request to is being cancelled.

***

### `/tpayes`

**Usage:** `/tpayes [Player Name]`\
**Description:** Accepts a specified teleport request.\
**Permission:** `at.member.yes`\
**Aliases:** `/tpaccept`, `/tpyes`\
**Arguments:**

* `[Player Name]` - the name of the player whose request is being accepted.

***

### `/tpano`

**Usage:** /tpano \[Player Name]\
**Description:** Denies a specified teleport request.\
**Permission:** at.member.no\
**Aliases:** /tpdeny, /tpno\
**Arguments:**

* `[Player Name]` - the name of the player whose request is being denied.

***

### `/tpblock`

**Usage:** /tpblock \<Player Name>\
**Description:** Blocks a specified player from sending teleport requests to you.\
**Permission:** at.member.block\
**Arguments:**

* `<Player Name>` - the name of the player to be blocked.

***

### `/tpunblock`

**Usage:** /tpunblock \<Player Name>\
**Description:** Unblocks a specified player, allowing them to send teleport requests to you again.\
**Permission:** at.member.unblock\
**Arguments:**

* `<Player Name>` - the name of the player to be unblocked.

***

### `/tpalist`

**Usage:** /tpalist \[Page Number]\
**Description:** Lists pending teleport requests directed to you.\
**Permission:** at.member.tpalist\
**Arguments:**

* `[Page Number]` - the page number of TPA requests to be shown.

***

### `/toggletp`

**Usage:** /toggletp \[Player Name]\
**Description:** Lets you switch between receiving TP requests or blocking them.\
**Permission:** at.member.toggletp\
**Argument:**

* `[Player Name]` - The player to have their teleportation toggled, requires the permission `at.admin.toggletp`

***

### `/tpon`

**Usage:** /tpon\
**Description:** Lets you receive TP requests.\
**Permission:** at.member.on

***

### `/tpoff`

**Usage:** /tpoff\
**Description:** Stops you receiving teleport requests.\
**Permission:** at.member.off

***

### `/rtp`

**Usage:** /rtp \[World Name] \[Player Name]\
**Description:** Teleports you, or a specified player, to a random location in either the given world, the world they are currently in or the first world in the whitelist should it be enabled.\
**Permission:** at.member.tpr\
**Aliases:** /tpr\
**Arguments:**

* `[World Name]` - The name of the world that /rtp is to be used in. Requires `at.member.tpr.other`. It cannot be used to bypass the world whitelist.
* `[Player Name]` - The name of the player to be randomly teleported. Requires a world name to be specified in front. Also requires the sender to have the permission `at.admin.tpr.other`.

***

### `/warp`

**Usage:** /warp \<Warp Name>\
**Description:** Teleports you to a specified warp.\
**Permission:** at.member.warp\
**Arguments:**

* `<Warp Name>` - The name of the warp to be teleported to.

***

### `/warps`

**Usage:** /warps\
**Description:** Either opens up a GUI or sends the player a list of warps, depending on what is specified in the config.\
**Permission:** at.member.warps

***

### `/spawn`

**Usage:** /spawn \[ID]\
**Description:** Teleports you to your world's spawnpoint or the spawnpoint with the specified ID.\
**Permission:** at.member.spawn\
**Arguments:**

* `[ID]` - The ID of the spawn to be teleported to.

***

### `/home`

**Usage:** /home \[Home Name|Player Name] \[Home Name]\
**Description:** Teleports you to your specified home point or your main home if no home is specified.\
**Permission:** at.member.home\
**Arguments:**

* `[Home Name]` - The name of the home to be teleported to.
* `[Player Name]` - The name of the player whose homes are to be teleported to and will replace the first `[Home Name]` argument when it is able to. Must have a home specified after it and the sender must have the permission `at.admin.home`. (Example: /home Thatsmusic99 chicken-nuggies)

***

### `/homes`

**Usage:** /homes \[Player Name]\
**Description:** Sends a list of homes to the user.\
**Permission:** at.member.homes\
**Arguments:**

* `[Player Name]` - The name of the player to have their homes listed. Must have the permission `at.admin.homes`.

***

### `/sethome`

**Usage:** /sethome \<Home Name>|(\<Player Name> \<Home Name>)\
**Description:** Sets a home for either yourself or a specified player at your current location.\
**Permission:** at.member.sethome\
**Arguments:**

* `<Home Name>` - The name of the home to be set.
* `<Player Name>` - The name of the player to have a home set for them. Must have a home name specified after it and must have the permission `at.admin.sethome`.

***

### `/delhome`

**Usage:** /delhome \<Home Name>|(\<Player Name> \<Home Name>)\
**Description:** Deletes one of your own homes or another player's home.\
**Permission:** at.member.delhome\
**Arguments:**

* `<Home Name>` - The name of the home to be deleted.
* `<Player Name>` - The name of the player to have their home deleted. Must have a home name specified after it and must have the permission `at.admin.delhome`.

***

### `/movehome`

**Usage:** /movehome \<Home Name>|(\<Player Name> \<Home Name>)\
**Description:** Moves either one of your own homes or another player's home.\
**Permission:** at.member.movehome\
**Arguments:**

* `<Home Name>` - The name of the home to be moved.
* `<Player Name>` - The name of the player to have their home moved. Must have a home name specified after it and must have the permission `at.admin.movehome`.

***

### `/setmainhome`

**Usage:** /setmainhome \<Home Name>|(\<Player Name> \<Home Name>)\
**Description:** Sets your own or another player's main home. If the home name specified does not represent an existing home, one will be set.\
**Permission:** at.member.setmainhome\
**Arguments:**

* `<Home Name>` - The name of the home to be considered the player's main home.
* `<Player Name>` - The name of the player to have a main home set. Must have a home name specified after it and must have the permission `at.member.setmainhome`.

***

### `/back`

**Usage:** /back\
**Description:** Returns you to your previous location.\
**Permission:** at.member.back

***

### `/at info`

**Usage:** /at info\
**Description:** Shows the majority of plugin information, such as version.\
**Permission:** at.member.core.info

***

### `/at help`

**Usage:** /at help \[Category]|\[Page Number]\
**Description:** Shows the help menu for commands depending on the section specified.\
**Permission:** at.member.core.help\
**Arguments:**

* `[Category]` - A category of which includes any of the following: `Teleport`, `Warps`, `Spawn`, `RandomTP`, `Homes` and `Admin`. Extra commands are provided with the permission `at.admin.help`.
* `[Page Number]` - The page in the help menu to check.
