# 💀 Death Management

AdvancedTeleport can handle where players teleport if they die. This is largely handled through the config.yml file itself.

## Presentation

```yaml
death-management:
  default: bed;spawn
  world: default
```

Some options are separated by `;` - if the first option (e.g. `bed`) does not have a location, then it falls back onto the second option (`spawn`), and so on.

If no location is found with any option, then AdvancedTeleport does not make any changes to death locations - other plugins may take over, or Minecraft itself will set the respawn point of a player.

If you don't want AdvancedTeleport to handle death management at all, you can just disable it by setting a blank string:

```yaml
death-management:
  default: ''
```

Or instead of doing it for `default`, do it for another world name:

```yaml
death-management:
  default: bed;spawn
  minigame-world: ''
```

## Teleportation Options

There are numerous different options to use, including:

* `tpr:world`
* `spawn`
* `home`
* `bed`
* `warp:name`

### `tpr:world`

Upon respawning, teleports the player to a random location in a specified world. This has to use Paper (or a fork of paper) and have `use-rapid-response` enabled so that locations are prepared prior to sending the player away.

The `world` part changes according to the world being teleported to, e.g.:

```yaml
death-management:
  default: tpr:survival
```

To teleport into a random location within the world `survival`.

### `spawn`

The player is teleported to the AdvancedTeleport-decided spawnpoint for the world they died in, similar to if they did `/spawn` instead of dying.&#x20;

### `home`

The player is teleported back to their main home.

### `bed`

The player is teleported back to their bed, in similar Vanilla fashion.

### `warp:name`

The player is teleported to a specified warp. Like with `tpr:world`, the `name` varies depending on the warp name itself, e.g. if we have a warp called `market`:

```yaml
death-management:
  default: warp:market
```
