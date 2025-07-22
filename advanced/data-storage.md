---
description: >-
  How the data storage of AdvancedTeleport works and how it can be edited
  manually.
---

# 💾 Data Storage

AdvancedTeleport stores data using MySQL or SQLite (default option), a common storage method for other plugins. All persistent data (e.g. homes, warps, player data and blocklist) are stored in these files.

{% hint style="info" %}
As it should be with the majority of plugins, no data stored within AdvancedTeleport is sent to external services - only the standard statistics are sent to [bStats](https://bstats.org/plugin/bukkit/AdvancedTeleport/5146#!) to understand the plugin's demographic.&#x20;
{% endhint %}

It is entirely possible to tweak some of the data in these files, and is often checked in the event that certain homes/warps/etc. are not loading. This page goes over how to read and write to the data storage of AdvancedTeleport safely.

{% hint style="danger" %}
Before making any changes to the MySQL database tables or SQLite file, ensure that the server is offline. Making changes to these files whilst the server is online can lead to inconsistencies or even data loss. \
\
In addition, **editing the data in the database/file is not recommended**. Only follow this guide if you know what you're doing. If you're not entirely sure about what you want to do, either edit the data through commands in-game, or reach out to plugin support.
{% endhint %}

## Reading data.db

If you want to manually tweak the SQLite data file, then you'll need a special program to do so.&#x20;

The often recommended option (and used by developers of the plugin) is [DB Browser for SQLite](https://sqlitebrowser.org/). It may look slightly unfamiliar to those who haven't used it before, but if you're looking to check the data itself, then the `Browse Data` tab is the only tab you need.

`// TODO`

## Reading an external MySQL Server

`// TODO`
