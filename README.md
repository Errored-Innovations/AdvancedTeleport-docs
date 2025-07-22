---
description: Welcome to the AdvancedTeleport wiki!
cover: >-
  .gitbook/assets/68747470733a2f2f6d656469612e646973636f72646170702e6e65742f6174746163686d656e74732f3533373636393231303532303831333536382f3737373938313734333738353138313232362f61745f7469746c652e706e673f77696474683d31343433266865696768743d3.png
coverY: 0
---

# 🏠 /home

This is a plugin written by Niestrat99 and Thatsmusic99 - it has been in ongoing development since 2019. It now looks to change how teleportation is used in Minecraft servers.

## Using this Wiki

A lot of this wiki goes over configuration options in more depth, as well as in certain use cases. A lot of options are in the config.yml file. If you are struggling to find a certain option, you are often able to find it using the `CTRL+F` keybind, then entering the option you are searching for.

This wiki itself is still a work in progress, but it can be contributed to.

## Requirements

AdvancedTeleport is intended for use from 1.18.x to 1.20.x. When a new Minecraft version (major or minor) is released, it is expected to work without issues. Nonetheless, the plugin is tested as soon as possible following release.

{% hint style="warning" %}
1.8 to 1.17.1 support has been dropped by the v6 series. Legacy support for v5 is still available, but only bugfixes are made.
{% endhint %}

For economy support, [Vault](https://www.spigotmc.org/resources/vault.34315/) and an economy plugin of your choice (such as Essentials) is required.

Spigot is the minimum software supported by AdvancedTeleport - Paper is required to validate performance concerns. Since AT is a teleport plugin, it is expected to have a performance impact by loading chunks when teleporting, especially randomly. However, I (Thatsmusic99) am especially knowledgeable with server optimisation, and I will be more than happy to help ensure your server can run properly with the plugin.

## Building

AdvancedTeleport is open-source on Github [here](https://github.com/Niestrat99/AT-Rewritten). To build v5, the command used is `mvn clean install -Denv.BUILD_NUMBER=PRIVATE`, where the build number is set to private and nothing else.

To build v6, just do `./gradlew AdvancedTeleport-Bukkit:slimJar`. To test and debug on a server, do `./gradlew runServer`.

## Support

Although AdvancedTeleport has a discussion forum on SpigotMC, the main form of support most people look for is through our [Discord](https://discord.gg/mgWbbN4) server. If you believe you have found a bug or have a suggestion, you are also free to have it posted on [Github](https://github.com/Niestrat99/AT-Rewritten/issues).

## Contributions

AdvancedTeleport would not be where it is today if it was not for the brilliant work of its contributors. To cover each one and what they have done for the plugin:

* [Niestrat99](https://github.com/Niestrat99) - plugin author
* [Thatsmusic99](https://github.com/Thatsmusic99) - plugin developer, overlord of pull request abuse
* [SuspiciousLookingOwl](https://github.com/SuspiciousLookingOwl) - sound notifications for /tpa and /tpahere, homes and warps can be interacted within /homes and /warps, and the warps GUI. ([#12](https://github.com/Niestrat99/AT-Rewritten/pull/12), [#14](https://github.com/Niestrat99/AT-Rewritten/pull/14), [#16](https://github.com/Niestrat99/AT-Rewritten/pull/16), [#17](https://github.com/Niestrat99/AT-Rewritten/pull/17))
* [siaynoq](https://github.com/siaynoq) - cancel teleportation on movement rather than just rotation ([#8](https://github.com/Niestrat99/AT-Rewritten/pull/8))
* [TheMrEngMan](https://github.com/TheMrEngMan) - choose where to apply the server cooldown ([#27](https://github.com/Niestrat99/AT-Rewritten/pull/27))
* [jonas-t-s ](https://github.com/jonas-t-s)- /back search radius, Floodgate API usage ([#42](https://github.com/Niestrat99/AT-Rewritten/pull/42), [#50](https://github.com/Niestrat99/AT-Rewritten/pull/50))
* [YouHaveTrouble](https://github.com/Niestrat99/AT-Rewritten/pull/55) - "tiny changes" yeah, right ([#55](https://github.com/Niestrat99/AT-Rewritten/pull/55))
* [Geolykt](https://github.com/Geolykt) - selectors (@a, @p) can be used in /tpr ([#61](https://github.com/Niestrat99/AT-Rewritten/pull/61))
* [DaRacci](https://github.com/DaRacci) - improved RTP options, per-world settings for RTP, claim plugin hooks ([#76](https://github.com/Niestrat99/AT-Rewritten/pull/76))

I would like to note this only accounts for major plugin changes, and does not account for minor changes such as typo fixes and compilation corrections (covered by contributors such as SuspiciousLookingOwl, Geolykt and animeavi).
