---
description: Frequently asked questions about the plugin.
---

# FAQ

### How do I disable /back?

You can add it to the disabled-commands list in the config.yml file:

```yaml
disabled-commands:
- back
```

### What's a permissions plugin?

No, seriously, this gets asked at least every week.

A permission plugin lets you manipulate what a specific set of players can use or access through permission nodes. LuckPerms is the most recommended plugin to use for this due to its rich diagnostic tools and web GUIs.

### How do I limit the number of homes someone can use?

To change the default homes limit, the `default-homes-limit` option in the config.yml can be changed to an integer value.

With permission plugins though, this value can be altered per-group by providing them with the permission `at.member.homes.<Number>` - for example, `at.member.homes.5`.

### Why are people respawning at the world spawn instead of their beds?

The default death management settings teleport players to the world spawn instead of their beds.

To change this, configure the death-management so it redirects players to their bed:

```yaml
death-management:
  default: bed
```

### Does AdvancedTeleport support networks (e.g. Bungeecord)?

No - whilst there are ideas to draft a Velocity and Bungeecord equivalent to AdvancedTeleport, there is nothing set in stone at this time.

Input on what could become of such a plugin though (e.g. what would it be useful for?) is more than welcome.

### Does AdvancedTeleport work with Essentials?

The two plugins are entirely separate - if you have both on the same server though, AdvancedTeleport will automatically override Essentials' commands. You will need to use in-built server mechanics to make either Essentials' commands override AT's commands, disable the commands you don't want from AT using the `disabled-commands` option in AT's config.yml, configure Essentials as necessary or see about Bukkit's brilliant commands.yml file here: [https://bukkit.fandom.com/wiki/Commands.yml](https://bukkit.fandom.com/wiki/Commands.yml)

You can also import plugin data from Essentials at AT or vice versa.

### How do you delete a home?

Using `/delhome <Home Name>`.
