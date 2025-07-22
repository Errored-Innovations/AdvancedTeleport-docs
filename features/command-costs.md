---
description: How to manage costs in AdvancedTeleport.
---

# 💸 Command Costs

You can make certain commands cost a certain value before a player can use them.&#x20;

As of currently, this applies to the following commands:

* [`/tpa`](../commands/member-commands.md#tpa)&#x20;
* [`/tpahere`](../commands/member-commands.md#tpahere)&#x20;
* [`/home`](../commands/member-commands.md#home)&#x20;
* [`/back`](../commands/member-commands.md#back)&#x20;
* [`/warp`](../commands/member-commands.md#warp)
* [`/spawn`](../commands/member-commands.md#spawn)&#x20;
* [`/tpr`](../commands/member-commands.md#rtp)&#x20;

{% hint style="info" %}
In the future, this should also support /sethome and /setwarp.&#x20;
{% endhint %}

## Vault

If you have Vault and a compatible economy plugin, you can use the currency from that plugin.

It's as simple as specifying how much you want to charge in the config:

```yaml
cost-amount: 100.0
```

AT will then use the default economy Vault chooses. If you want to verify which plugin this is, you can simply do `/vault-info`. If you want to use a certain plugin, you can add a prefix with the plugin name:

```yaml
cost-amount: Essentials:100.0
```

## Items



## Levels and EXP Points



## Cost Combinations
