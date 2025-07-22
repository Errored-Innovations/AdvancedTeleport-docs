---
description: Covers random teleportation options and settings.
---

# ✈️ Random Teleportation

In AdvancedTeleport, random teleportation is flexible and robust to allow it to adapt to different use cases. It is enabled by the `use-randomtp` option in the config.yml file.

```yaml
use-randomtp: true
```

## Commands

Random Teleportation only has one command dedicated to it.

* [`/tpr`](../commands/member-commands.md#rtp)

## Basic Usage

For the majority of players, using `/tpr` only involves using the command itself to be sent to a random location in the world. In that case, only the permission `at.member.tpr` is required for use.

In order to use `/tpr [World]` to randomly teleport into another world, the player needs permission `at.member.tpr.other`. However, this permission is not required if you only want players to randomly teleport in certain worlds.

## Admin Usage

Administrators have a bit more leeway with the command, or even players themselves depending on how you set up permissions.

If an admin has the permission `at.admin.tpr.other`, they are able to teleport other players to different worlds using `/tpr [World] [Player]`.

{% hint style="warning" %}
This does not override restrictions on whitelisted worlds


{% endhint %}

## Borders

You can set boundaries in worlds to stop players from exceeding defined limits and generating too much of the world.

### v5

In v5, there are four options to set for boundaries via the plugin, and these boundaries cannot be per-world without the use of [alternative borders](random-teleportation.md#alternative-borders). By default, the options are as follows:

```yaml
maximum-x: 5000
maximum-z: 5000
minimum-x: -5000
minimum-z: -5000
```

This means that players that use `/tpr` (unless being handled by the alternative borders) will not be teleported outside of 5000x, \~y, 5000z to -5000x, \~y, -5000z. They have a square radius of 5000.

### v6

In v6, the system is a bit different, since it supports differing borders in different worlds.

### Alternative Borders

AdvancedTeleport has the capabilities to let other plugins or systems decide the border that RTP is limited to, with this feature being available to both v5 and v6.

## Rapid Response (Prepared Locations)

Rapid Response allows AT to prepare random teleportation locations in advance before the command is run by players. This means when players run `/tpr`, they can be immediately teleported rather than have to wait for the plugin to find a location.

{% hint style="warning" %}
This feature is only available on Paper and its forks due to performance concerns.
{% endhint %}

To enable Rapid Response, just set `use-rapid-response` to true in the config.yml file under the RandomTP section. This is often enabled by default regardless.

```yaml
use-rapid-response: true
```

### Prepared Locations Limit

The `prepared-locations-limit` option defines the number of locations that get prepared in each world. The default limit is 3.

```yaml
prepared-locations-limit: 3
```

## World Whitelisting

If you have a lobby world but want players to only randomly teleport in given worlds, then you are able to redirect players to those worlds easily.

{% hint style="warning" %}
If you are an administrator on the server or OPed, you may automatically bypass these restrictions with the permission `at.admin.rtp.bypass-world`. If you do not want this behaviour, you have to negate the permission.
{% endhint %}

For example, let's say you have the following worlds:

* `lobby` - where players first spawn.
* `survival` - where you want players to RTP in.
* `survival_nether` - the Nether world for the survival world.

And we only want players to use /rtp in the survival world, but also want players to use `/tpr` in the `lobby` world to go to `survival`. This is possible in AdvancedTeleport.

If `whitelist-worlds` is enabled, then the plugin automatically locks the use of `/tpr` to the specified worlds in the `allowed-worlds` list.

```yaml
whitelist-worlds: true
```

```yaml
allowed-worlds:
- survival
```

If we enable `redirect-to-whitelisted-worlds` too, then using `/tpr` in `lobby` and `survival_nether` would redirect players to `survival`.

```yaml
redirect-to-whitelisted-worlds: true
```

## Ignored World Generators

`// TODO`

## Location Requirements

There are location requirement options that stop players from being teleported to less than ideal locations, such as the middle of the ocean. It is more efficient to check biomes than individual blocks.

The biomes to avoid are listed in the `avoid-biomes` option, and biomes you can add are available [here](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/Biome.html).&#x20;

```yaml
avoid-biomes:
- OCEAN
- DEEP_OCEAN
```

For individual blocks, the `avoid-blocks` option is used.&#x20;



## Performance

Random teleportation is a difficult feature to master in plugins, and it was no different for AdvancedTeleport. However, like most plugins, there will be a significant performance impact on the server if it is not set up for random teleportation.

For the unaware, when the `/tpr` command is used, it will pick a random set of coordinates, load the chunks at those coordinates and verify that the location is suitable for teleportation. However, if the chunks have not been generated, then the server will do that too, and it can cause considerable lag on the server.

Here's some ways to help you optimise Random Teleportation for AdvancedTeleport on your server.

### Paper

Using Paper as your server type instead of Spigot is generally the best way to start.

AdvancedTeleport takes advantage of Paper's asynchronous chunk loading and teleportation features, meaning that chunk loading and teleportation should not have an impact on the rest of the server.

If you are using a fork of Paper, like Purpur or Pufferfish, then those will count towards the performance improvements.

### Rapid Response

If you're on Paper, you can also enable the [Rapid Response](random-teleportation.md#rapid-response-prepared-locations) feature, so that locations are prepared in advance. The locations picked in advance also generate any chunks at a low priority, unlike at a high priority if a location has to be picked as soon as the player runs the command.

### Map-Pregeneration

If you've exhausted these options but still haven't had much luck optimising the feature, you will have to try pre-generating the map.

## Miscellaneous

`// TODO`
