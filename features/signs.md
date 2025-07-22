---
description: An overview of signs that can be used in AT.
---

# 🚸 Signs

AdvancedTeleport has a feature that allows players to set up signs that carry out different functions.

## Setting up signs

To set up signs, you need to have permission to create those signs. For the majority of cases, this is `at.admin.sign.<type>.create`, e.g. `at.admin.sign.warp.create`.

Then, you are able to place a sign of any type. On the first line, type the sign you want, e.g. `[Warps]`. If the sign was successfully made, the first line of text should turn a blue and bold colour. Otherwise, the text will not change at all, and the sign will not respond when clicked.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

## Using signs

In order to use signs, players will need a permission to use them. This permission is `at.member.<type>.use-sign`, e.g. `at.member.warp.use-sign`. From there, if the sign is valid, the player can right-click (or interact) with the sign for it to work.

{% hint style="warning" %}
If players can't interact with signs, spawn protection will also stop them from being interacted with altogether - make sure spawn protection is either disabled or that signs are outside of the spawn area, and also check any protection plugins you have on the server as well.
{% endhint %}

## Sign Types

### \[Warps]

The `[Warps]` sign simply runs the `/warps` command on players' behalf to show what warps they can teleport to. It is only set up by having `[Warps]` on the first line.

* Permission to create: `at.admin.sign.warps.create`
* Permission to use: `at.member.warps.use-sign`
* Required feature: `use-warps`

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>An example of the [Warps] sign.</p></figcaption></figure>

### \[Warp]

The `[Warp]` sign teleports the player who clicks it to the specified warp. On the first line is the `[Warp]` identifier, but on the second line is the warp name, e.g. `MySpecialWarp`, with it being case-sensitive.

The player also needs an extra permission, `at.member.warp.sign.<warp>` (e.g. `at.member.warp.sign.myspecialwarp`), but this is often provided by default via `at.member.warp.sign.*`.

{% hint style="warning" %}
Note how the warp name in the permission `at.member.warp.sign.myspecialwarp` is all in lowercase, despite its name having some uppercase characters - if you add the permission with uppercase characters, then the permission will not work/be picked up.
{% endhint %}

* Permission to create: `at.admin.sign.warp.create`
* Permission to use: `at.member.warp.use-sign` and `at.member.warp.sign.<name>`
* Required feature: `use-warps`

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption><p>An example of the [Warp] sign.</p></figcaption></figure>

### \[Spawn]

The `[Spawn]` sign teleports the player to either a specified spawnpoint, or the resulting spawnpoint that is selected for the player.&#x20;

If the second line is empty, then the spawn is selected just like how `/spawn` would run. For more information on how the destination of this is chosen, check the [spawnpoints page](spawnpoints.md#spawn-selection-algorithm).

If a spawn or world name is specified on the second line, then the spawn is selected just like how `/spawn [ID]` would run.

* Permission to create: `at.admin.sign.spawn.create`
* Permission to use: `at.member.spawn.use-sign`
* Required feature: `use-spawns`

### \[RandomTP]

The `[RandomTP]` sign teleports the player to a random location in the world. If there is a world specified on the second line, then the player is teleported to that world.

* Permission to create: `at.admin.sign.randomtp.create`
* Permission to use: `at.member.randomtp.use-sign`
* Required feature: `use-randomtp`

### \[Bed]

The `[Bed]` sign teleports the player to their bed. Costs, warm-ups and cooldowns are taken into account when the player interacts with the sign. If the player does not have a bed home, then the sign does not respond.

* Permission to create: `at.admin.sign.bed.create`
* Permission to use: `at.member.bed.use-sign`
* Required feature: `use-homes`

### \[Home]

The `[Home]` sign teleports the player to their main home. If the player has no main home but has several normal homes, then the sign picks the first one to send the player to. If the player has no homes, the sign does not respond.

Unlike signs such as `[Warp]` and `[RandomTP]`, there is no second line specified for this sign.

* Permission to create: `at.admin.sign.home.create`
* Permission to use: `at.member.home.use-sign`
* Required feature: `use-homes`

### \[Homes]

`// TODO` (for some reason this exists in the code and is registered but doesn't actually do anything so I should probably look into that)
