---
description: Dynamic permissions for v6 and how they work
---

# Dynamic Permissions

Dynamic Permissions is a new feature added in v6 that allows you to set up permissions for an individual group or player so that you can make cooldowns, distance limitations, costs and warm-ups unique to them rather than use the central configurations for everyone.

### Dynamic Permissions and Custom Configuration

Custom configuration is preferred over dynamic permissions as it will wound up being more efficient than dynamic permissions. However, dynamic permissions are easier to assign outright, whilst custom configuration requires setup in the config.yml file. In addition, some options can only use custom configuration.

### Per-command options

When prompted with per-command permissions, you can use the following as options:

* `tpa` - for /tpa.
* `tpahere` - for /tpahere.
* `back` - for /back
* `home` - /home
* `warp` - /warp
* `tpr` - for /tpr, /rtp
* `spawn` - for /spawn

### Per-world options

When using world names in the permissions, it must use the IDs of the world. For example, if the display name of a world is Survival but it's actually svworld, use svworld. If a world ID has capital letters in it, put the permission in lowercase. As an example, if the world ID is Survival, use `at.member.cooldown.survival.5`.

## Cooldowns

### Dynamic Permissions

* To add a cooldown of 5 seconds, you can easily just use the permission `at.member.cooldown.5`.
* To make it per-command, use `at.member.cooldown.<command>.5`. As an example of this for the /tpa command, `at.member.cooldown.tpa.5`.
* To make it depend on the world you are teleporting to, use `at.member.cooldown.<world>.5`. For example, `at.member.cooldown.world.5` to receive a cooldown of 5 seconds when teleporting to world.
* To make it best of both, use `at.member.cooldown.<command>.<world>.5`.

The value of 5 can be replaced with any integer value.

The lowest values assigned are prioritised over higher values. Because of this, if you give a higher-weighting group (such as Moderator) a cooldown of 5 seconds but it inherits a group with a cooldown of 3 seconds, the moderator group will have a cooldown of 3 seconds. The work-around for this is to negate the permission `at.member.cooldown.3` for the group, or use custom configuration.

### Custom Configuration

The configuration section for this is `custom-cooldowns`, and requires a format of the following:

```yaml
custom-cooldowns:  
  vip-cooldown: 5
  mvp-cooldown: 3
```

Groups further down the list are prioritised more than the ones above it. To assign a group as a permission, use `at.member.cooldown.<group>`, such as `at.member.cooldown.vip-cooldown`.&#x20;

* These can also be assigned per-command, such as `at.member.cooldown.tpa.vip-cooldown`.
* These can be assigned by destination world too, such as `at.member.cooldown.world.vip-cooldown`.
* For both, use something similar to `at.member.cooldown.tpa.world.vip-cooldown`.

## Warm-ups

### Dynamic Permissions

* To add a warm-up of 5 seconds, you can easily just use the permission `at.member.timer.5`.
* To make it per-command, use `at.member.timer.<command>.5`. As an example of this for the /tpa command, `at.member.timer.tpa.5`.
* To make it depend on the world you are teleporting to, use `at.member.timer.<world>.5`. For example, `at.member.timer.world.5` to receive a warm-up of 5 seconds when teleporting to world.
* To make it best of both, use `at.member.timer.<command>.<world>.5`.

The value of 5 can be replaced with any integer value.

The lowest values assigned are prioritised over higher values. Because of this, if you give a higher-weighting group (such as Moderator) a warm-up of 5 seconds but it inherits a group with a warm-up of 3 seconds, the moderator group will have a warm-up of 3 seconds. The work-around for this is to negate the permission `at.member.timer.3` for the group, or use custom configuration.

### Custom Configuration

The configuration section for this is `custom-warm-ups`, and requires a format of the following:

```yaml
custom-warm-ups:  
  vip-warmup: 5
  mvp-warmup: 3
```

Groups further down the list are prioritised more than the ones above it. To assign a group as a permission, use `at.member.timer.<group>`, such as `at.member.timer.vip-cooldown`.&#x20;

* These can also be assigned per-command, such as `at.member.timer.tpa.vip-warmup`.
* These can be assigned by destination world too, such as `at.member.timer.world.vip-warmup`.
* For both, use something similar to `at.member.timer.tpa.world.vip-warmup`.
