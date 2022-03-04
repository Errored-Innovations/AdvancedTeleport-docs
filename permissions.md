# Permissions

This page lists all of the existing permissions in AdvancedTeleport.

{% hint style="info" %}
All permissions starting with at.member are given to everyone automatically, with an exception for a select few permissions.
{% endhint %}

### Member Permissions

| Permission                  | Description                                                                                            |
| --------------------------- | ------------------------------------------------------------------------------------------------------ |
| at.member.back              | Allows a player to use /back.                                                                          |
| at.member.back.death        | Allows a player to teleport to their death location using /back.                                       |
| at.member.block             | Allows a player to use /tpblock.                                                                       |
| at.member.cancel            | Allows a player to use /tpcancel.                                                                      |
| at.member.delhome           | Allows a player to use /delhome.                                                                       |
| at.member.here              | Allows a player to use /tpahere.                                                                       |
| at.member.home              | Allows a player to use /home.                                                                          |
| at.member.homes             | Allows a player to use /homes.                                                                         |
| at.member.homes.<#>         | Allows a player to set a specific number of homes (e.g. 5).                                            |
| at.member.homes.location    | Allows a player to see their home location when checking /homes.                                       |
| at.member.list              | Allows a player to view their tpa requests using /tpalist.                                             |
| at.member.movehome          | Allows a player to move their home using /movehome.                                                    |
| at.member.no                | Allows a player to deny a teleport request using /tpno.                                                |
| at.member.off               | Allows a player to disable teleportation requests.                                                     |
| at.member.on                | Allows a player to enable teleportation requests.                                                      |
| at.member.randomtp.use-sign | Allows a player to use a \[RandomTP] sign.                                                             |
| at.member.sethome           | Allows a player to set a home using /sethome.                                                          |
| at.member.setmainhome       | Allows a player to set a main home using /setmainhome                                                  |
| at.member.spawn             | Allows a player to teleport to the main spawnpoint using /spawn.                                       |
| at.member.spawn.\<ID>       | Allows a player to teleport to a specific spawnpoint with the specified ID.                            |
| at.member.spawn.use-sign    | Allows a player to use a \[Spawn] sign.                                                                |
| at.member.toggletp          | Allows a player to use /toggletp.                                                                      |
| at.member.tpa               | Allows a player to use /tpa.                                                                           |
| at.member.tpr               | Allows a player to use /tpr.                                                                           |
| at.member.unblock           | Allows a player to use /tpunblock.                                                                     |
| at.member.warp              | Allows a player to use /warp.                                                                          |
| at.member.warp.\<Warp>      | Allows a player to teleport to a specific warp. `at.member.warp.*` is provided to everyone by default. |
| at.member.warp.use-sign     | Allows a player to use a \[Warp] sign.                                                                 |
| at.member.warps             | Allows a player to use /warps.                                                                         |
| at.member.warps.location    | Allows a player to view the location of a warp in /warps.                                              |
| at.member.yes               | Allows a player to use /tpayes.                                                                        |

### Core Permissions

| Permission            | Description                               |
| --------------------- | ----------------------------------------- |
| at.member.core        | Gives a player access to the /at command. |
| at.member.core.export | Allows a player to use /at export.        |
| at.member.core.help   | Allows a player to use /at help.          |
| at.member.core.import | Allows a player to use /at import.        |
| at.member.core.info   | Allows a player to use /at info.          |
| at.member.core.purge  | Allows a player to use /at purge.         |
| at.member.core.reload | Allows a player to use /at reload.        |

### Admin Permissions

| Permission                       | Description                                                                                  |
| -------------------------------- | -------------------------------------------------------------------------------------------- |
| at.admin.all                     | Allows a player to use /tpall.                                                               |
| at.admin.bypass.cooldown         | Allows a player to bypass the command cooldown.                                              |
| at.admin.bypass.distance-limit   | Allows a player to bypass the distance limit.                                                |
| at.admin.bypass.payment          | Allows a player to bypass payments.                                                          |
| at.admin.bypass.teleport-limit   | Allows a player to bypass teleport limitations.                                              |
| at.admin.bypass.teleport-on-join | Allows a player to bypass the teleportation on join function.                                |
| at.admin.bypass.timer            | Allows a player to bypass the warm-up timer.                                                 |
| at.admin.delhome                 | Allows a player to delete another player's homes using /delhome.                             |
| at.admin.delwarp                 | Allows a player to delete a warp using /delwarp.                                             |
| at.admin.home                    | Allows a player to teleport to the homes of another player.                                  |
| at.admin.homes                   | Allows a player to access another player's homes.                                            |
| at.admin.mirrorspawn             | Allows a player to use the /mirrorspawn command.                                             |
| at.admin.movehome                | Allows a player to move another player's home.                                               |
| at.admin.notify                  | Notifies plays with this permission when a new update is available.                          |
| at.admin.removespawn             | Allows a player to use /removespawn.                                                         |
| at.admin.request-in-vanish       | Allows a player to make a /tpa request whilst invisible to another player.                   |
| at.admin.sethome                 | Allows a player to set a home for another player.                                            |
| at.admin.sethome.bypass          | Allows a player to bypass the /sethome limit.                                                |
| at.admin.setmainhome             | Allows a player to set a home for another player.                                            |
| at.admin.setmainspawn            | Allows a player to use /setmainspawn.                                                        |
| at.admin.setspawn                | Allows a player to use /setspawn.                                                            |
| at.admin.setspawn.other          | Allows a player set a spawn using /setspawn with a name included.                            |
| at.admin.setwarp                 | Allows a player to set a warp using /setwarp.                                                |
| at.admin.sign.bed.create         | Allows a player to create a sign with [Bed] on it.                                           |
| at.admin.sign.randomtp.create    | Allows a player to create a sign with [RandomTP] on it.                                      |
| at.admin.sign.spawn.create       | Allows a player to create a sign with [Spawn] on it.                                         |
| at.admin.sign.warp.create        | Allows a player to create a sign with [Warp] on it.                                          |
| at.admin.sign.warps.create       | Allows a player to create a sign with [Warps] on it.                                         |
| at.admin.toggletp                | Allows a player to toggle teleportation status for another player.                           |
| at.admin.tploc                   | Allows a player to use /tploc.                                                               |
| at.admin.tploc.others            | Allows a player to teleport another player using /tploc.                                     |
| at.admin.tploc.safe-teleport     | Allows a player to safely teleport using /tploc without falling.                             |
| at.admin.tpo                     | Allows a player to use /tpo, which overrides a player's teleportation status.                |
| at.admin.tpoffline               | Allows a player to use /tpoffl, so they can teleport to an offline player.                   |
| at.admin.tpofflinehere           | Allows a player to use /tpofflh, so they can change the login location of an offline player. |
| at.admin.tpohere                 | Allows a player to use /tpohere.                                                             |
| at.admin.tpr.bypass-world        | Allows a player to bypass world restrictions on /tpr.                                        |
| at.admin.tpr.other               | Allows a player to teleport another player using /tpr.                                       |
| at.admin.tpr.other.selector      | Allows a player to teleport a selection of players using @p, @a, etc.                        |
