# ⭐ Spawnpoints

Spawnpoints can be considered a special type of warp - they're often the first point that a player is teleported to, whether it is in the server, or after they die. In AdvancedTeleport, they can also be referenced by an ID and be even more flexible than a standard spawn system.&#x20;

It is enabled by the `use-spawn` option in the config.yml, and is enabled by default.

```yaml
use-spawn: true
```

## Commands

The commands that fall under the spawn feature include:

* [`/mirrorspawn`](../commands/admin-commands.md#mirrorspawn)
* [`/removespawn`](../commands/admin-commands.md#removespawn)
* [`/setmainspawn`](../commands/admin-commands.md#setmainspawn)
* &#x20;[`/setspawn`](../commands/admin-commands.md#setspawn)
* &#x20;[`/spawn`](../commands/member-commands.md#spawn)

## Spawn Selection Algorithm

When a player does `/spawn` on its own with basic permissions, there is an algorithm that AdvancedTeleport executes to decide where the player is teleported to. It is as follows:

1. If the "nearest spawn" feature is enabled, then the nearest spawnpoint to the player is found. If there are no spawns in the player's world or they do not have permission to the spawns in the world, we go to step 3.
2. If there is a spawn that is named after the world that the player is in, it will fetch that spawn and verify the player can access it.&#x20;
   * If the spawn being checked cannot be accessed by the player and has a mirroring spawnpoint, then the mirroring spawnpoint is checked too.
   * If the final spawn cannot be accessed, then go to step 3.
3. As a final attempt, if there is a main spawn set, then just return it.
4. If no main spawn is set, then the plugin gets the spawnpoint of the world and returns it.

{% hint style="info" %}
In step 4, the plugin will return the overworld spawnpoint if the player is in the Nether or End by default, handled by the `use-overworld` option.
{% endhint %}

{% hint style="info" %}
A player will only have access to a spawnpoint if they have the permission `at.member.spawn.<Spawn ID>`. By default, all players have access to all spawnpoints. Players do not need permission to the main spawnpoint set.
{% endhint %}

```yaml
use-overworld: true
```

### Nearest Spawnpoint

The "nearest spawnpoint" feature picks out the nearest spawnpoint to the player when deciding on the `/spawn` or respawn location. It is enabled by the `teleport-to-nearest-spawnpoint` option.

```yaml
teleport-to-nearest-spawnpoint: true
```

## Basic Usage

To set a spawnpoint for the world you're in, you are able to just do `/setspawn` and it will set the spawnpoint as well as the main spawnpoint. If no ID is specified, it will use the world's name.

{% hint style="info" %}
The main spawnpoint is often considered the "default" spawn point players are sent to if all else fails. If you wish to change the main spawnpoint, you can use `/setmainspawn`.
{% endhint %}

If you're looking to have multiple spawnpoints for different players, you can use `/setspawn [ID]` to set an ID for each distinct spawnpoint.

The first spawnpoint you set in AT will be the main spawnpoint that players will teleport to if using `/spawn` or dying when AT is configured to handle death respawning.

If no spawn is set through AT but `/spawn` is used by a player, they will be teleported to the world's spawnpoint. If you don't intend for this to happen, use `/setspawn` to a point you want in the world.

## (New) Player Spawning

AdvancedTeleport has the ability to set new players' spawnpoint to a certain spawnpoint. If you want this featrue enabled, just have `teleport-to-spawn-on-first-join` set to true:

```yaml
teleport-to-spawn-on-first-join: true
```

When this option is enabled, players joining for the first time will be teleported to the main spawnpoint. However, if you want to use a different spawnpoint, you can set it to the ID of the spawnpoint you want:

```yaml
first-spawn-point: lobby
```

Where `lobby` is the name of the spawn you've set through `/setspawn [ID]`.&#x20;

{% hint style="info" %}
Remember that if you don't specify a spawn ID when using `/setspawn`, it uses the name of the world the spawn was set in.
{% endhint %}

If you want to change the first spawn point to just use the main spawnpoint again, just set the option to a blank string:&#x20;

```yaml
first-spawn-point: ''
```

## Mirroring Spawns

If you want to have a dynamic spawn system, you can mirror spawns so that players can go to a different spawnpoint if they don't have access to a certain one.

{% hint style="info" %}
As it stands, the mirror system isn't incredibly applicable and where it is, it's even less accessible. I'd like to make some improvements down the line that will improve its accessibility and consequently, its applicability, so this section doesn't go into heavy detail whilst those changes are pending.
{% endhint %}

