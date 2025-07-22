---
description: Covers home options in the plugin.
---

# 🏘️ Homes

Homes in AdvancedTeleport work similarly to other plugins that manage homes, with some extra bits and pieces for accessibility. It is enabled by the `use-homes` in the config.yml file.&#x20;

```yaml
use-homes: true
```

## Commands

Homes have a series of commands attached to it, including:

* [`/sethome`](../commands/member-commands.md#sethome)
* [`/home`](../commands/member-commands.md#home)
* [`/homes`](../commands/member-commands.md#homes)
* [`/delhome`](../commands/member-commands.md#delhome)
* [`/movehome`](../commands/member-commands.md#movehome)
* [`/setmainhome`](../commands/member-commands.md#setmainhome)

## Basic Usage

Players are easily able to set a home using [`/sethome`](../commands/member-commands.md#sethome). If they have set homes before, then they will need to specify a name (e.g. `/sethome Mineshaft`). Otherwise, it will automatically set the first home's name to `home`.

Players are able to teleport back to their homes using [`/home`](../commands/member-commands.md#home).  If only a single home is set for the player, the plugin will teleport the player to that home. Otherwise, if `show-homes-with-no-input` is enabled, then a list of homes is sent. If the option is disabled or the player has a main home set and `prioritise-main-home` is set to true, the player is teleported to their main home instead.

```yaml
show-homes-with-no-input: false
prioritise-main-home: true
```

To delete a home, players can do [`/delhome <Home Name>`](../commands/member-commands.md#delhome).&#x20;

To view a list of homes available to the player, they are able to use [`/homes`](../commands/member-commands.md#homes) or `/home list` (if the player does not have a home called `list`).

If players wish to move a home, they are able to use [`/movehome <Home Name>`](../commands/member-commands.md#movehome). If `overwrite-sethome` is enabled, then a player can use `/sethome <Home Name>` to move a home. However, the player will still need the `at.member.movehome` permission.

If a player wishes to change their main home, they can use `/setmainhome <Home Name>` to either set an existing home as their new main home, or a new home which is also set as their main home.

## Admin Usage

Administrators are able to manage players' homes

## Limiting Home Numbers

You can limit the number of homes that can be set by players in AdvancedTeleport through various means. The most obvious example is the `default-homes-limit` option in the config.yml file, which can be set to any value.

If the value is set to -1, players can set as many homes as they like.

```yaml
default-homes-limit: 3
```

To set the limit on homes depending on various factors (e.g. player groups), then an individual permission, `at.member.homes.<#>` is used.

For example, if the default homes limit is 3, but you want the VIP group to have a limit of 5 homes, you would give the VIP group the permission `at.member.homes.5`.

If you have a higher group such as MVP that inherits from VIP (for some bizarre reason) and has permission `at.member.homes.1`, then the 5-home limit from VIP would take precedence. To avoid this, you would need to negate the `at.member.homes.5` permission in the MVP group.

### Over the Homes Limit

If you change the homes limit for a certain player and they have more homes than the new limit, then there are ways to deal with it in AT.

You can deny players' access to their most recently set homes if they exceed the homes limit with the `deny-homes-if-over-limit` option in the config.yml file. To enable this, set the option to `true`.

```yaml
deny-homes-if-over-limit: true
```

The players will always be able to access their main homes unless they have a limit of 0. The players cannot set their main home to a home they cannot access.

To hide homes that players don't have access to, you can use the `hide-homes-if-denied` option. However, this could potentially confuse players if enabled.

```yaml
hide-homes-if-denied: false
```

## Accessibility

There are a few accessibility options in AT that can be toggled in the plugin. One example is the `overwrite-sethome` option, which when set to `true`, behaves the same as `/movehome` if a player uses `/sethome` on a home they already have.

Since AT did not always behave this way, the option is provided for version parity.

```yaml
overwrite-sethome: true
```

If players use `/home` on its own expecting a homes list to be pulled up, just to be teleported to their main home, you can disable this by setting the following options:

```yaml
show-homes-with-no-input: true
prioritise-main-home: false
```
