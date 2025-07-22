---
description: An overview of basic teleportation in the plugin.
---

# 🧳 Basic Teleportation

A quick overview of configuration and commands that fall under the Basic Teleportation feature of AdvancedTeleport. It is enabled through the `use-basic-teleport-features` in the config.yml file.

```yaml
use-basic-teleport-features: true
```

## Commands

Commands that fall under the basic teleportation branch include:

* `/back`
* `/toggletp`
* `/tpa`
* `/tpahere`
* `/tpall`
* `/tpblock`
* `/tpcancel`
* `/tphereoffline`
* `/tplist`
* `/tploc`
* `/tpno`
* `/tpo`
* `/tpoff`
* `/tpoffline`
* `/tpohere`
* `/tpon`
* `/tpunblock`
* `/tpyes`

## Back

Different from the rest, /back is a command that takes you to your previous location. If the player using the command also has the `at.member.back.death` permission, they can return to their last position if it was where they died. If they do not have permission, then their /back destination is unchanged.

{% hint style="info" %}
If you want to disable this command, you can add it to the `disabled-commands` list. See the FAQ or Miscellaneous section for more on this.
{% endhint %}

### Tracked Teleportation Causes

In order to function properly, /back only tracks specifically configured teleportation causes. The default configuration is the following:

```yaml
used-teleport-causes:
- COMMAND
- PLUGIN
- SPECTATE
```

Meaning the plugin will allow players to teleport back to prior locations if they teleported by any of the following methods (e.g. command, plugin, or the spectator menu).

There is a full list of teleport causes you can add to the list [here](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerTeleportEvent.TeleportCause.html).

{% hint style="warning" %}
The `UNKNOWN` teleportation tracks (mostly) regular movements and should not be added to the list.
{% endhint %}

### Search Radius

If a player dies in an unsafe location (e.g. in lava) and uses [`/back`](../commands/member-commands.md#back), the plugin will attempt to recalculate the location that the player teleports to so they are not in an unsafe position.&#x20;

The plugin searches a set number of blocks in a radius around this location (by default, this is 5 blocks) on the X, Y and Z axis. If no safe location is found in this area, the unsafe location is not changed.

```yaml
back-search-radius: 5
```

{% hint style="info" %}
If the search radius is set to `-1`, the feature is disabled.
{% endhint %}

## Teleportation Requests

One of the ways to teleport is by sending teleportation requests to another player.

To do this, do [`/tpa <player>`](../commands/member-commands.md#tpa) to ask to teleport to the player's location, or [`/tpahere <player>`](../commands/member-commands.md#tpahere) to ask them to teleport to your location. If the receiving player has teleportation disabled, the request will not go through.

`// TODO`

## Immediate Teleportation

`// TODO`

## Bedrock Support

`// TODO`
