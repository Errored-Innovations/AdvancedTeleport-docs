---
description: Covers warm-ups, the period before teleportation.
---

# 🔥 Warm-ups

Warm-ups are the period before a player teleports.

## Commands

The following commands have warm-ups:

* [`/tpa`](../commands/member-commands.md#tpa)
* [`/tpahere`](../commands/member-commands.md#tpahere)
* [`/tpr`](../commands/member-commands.md#rtp)
* [`/warp`](../commands/member-commands.md#warp)&#x20;
* [`/spawn`](../commands/member-commands.md#spawn)
* [`/home`](../commands/member-commands.md#home)
* [`/back`](../commands/member-commands.md#back)

{% hint style="info" %}
More flexibility with commands and warm-ups is planned.
{% endhint %}

## Base Configuration

The option that decides the default warm-up period for all commands is the `warm-up-timer-duration` option in the config.yml. It is measured in seconds.

<pre class="language-yaml"><code class="lang-yaml"># The number of seconds it takes for the teleportation to take place following confirmation.
# (i.e. "You will teleport in 3 seconds!")
# This acts as the default option for the per-command warm-ups.
<strong>warm-up-timer-duration: 3
</strong></code></pre>

To change the value per-command, there is a `per-command-warm-ups` option with each configurable command included.

```yaml
# Command-specific warm-ups.
per-command-warm-ups:
  # Warm-up timer for /tpa.
  tpa: default
  # Warm-up timer for /tpahere
  tpahere: default
  # Warm-up timer for /tpr, or /rtp.
  tpr: default
  # Warm-up timer for /warp
  warp: default
  # Warm-up timer for /spawn
  spawn: default
  # Warm-up timer for /home
  home: default
  # Warm-up timer for /back
  back: default
```

In order to change a warm-up for a specific command, you can just replace `default` with the duration of the warm-up you want, again in seconds:

```yaml
per-command-warm-ups:
  tpa: 5
```

And as a cool effect, if you want to give the player a little blindness during the warm-up, use the `blindness-on-warmup` option!

```yaml
# Gives the teleporting player a blindness effect whilst waiting to teleport.
blindness-on-warmup: true
```

### Movement

Warm-ups can cancel the teleportation altogether if the player moves. This can come in handy if the player tries to escape a sticky situation of having zombies beating them up, but you don't want them to escape - you're a psychopath and want them to not escape their suffering.

You are able to have movement cancel the teleportation altogether with the `cancel-warm-up-on-movement` option.

```yaml
# Whether or not teleportation should be cancelled upon movement only.
cancel-warm-up-on-movement: true
```

Or, harsher yet, cancel the teleportation if the player rotates slightly with the `cancel-warm-up-on-rotation` option.

```yaml
# Whether or not teleportation should be cancelled if the player rotates or moves.
cancel-warm-up-on-rotation: true
```

### Damage

You can additionally make warm-ups cancel when players take damage with the `cancel-warm-up-on-damage` option.

<pre class="language-yaml"><code class="lang-yaml"># Whether or not teleportation should be cancelled when the player receives damage.
# Best option to accompany the invulnerability system if your server has it enabled, so that players can't cheese it. :thumbsup:
<strong>cancel-warm-up-on-damage: true
</strong></code></pre>

## Dynamic Warm-ups

{% hint style="info" %}
This feature is only available on v6.
{% endhint %}

Dynamic warm-ups allow certain groups of players have certain warm-ups. There are two ways of handling this: the `custom-warm-ups` option, or using permissions.

{% hint style="info" %}
Using the `custom-warm-ups` option is more efficient than using the permissions method on its own, and will override it.
{% endhint %}

### Configuration Option

The `custom-warm-ups` section is the main method to allowing&#x20;
