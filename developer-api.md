---
description: AdvancedTeleport v6 has an extensive API that can be used by other plugins.
---

# ☄️ Developer API

## API Purpose

The aim of AdvancedTeleport v6 was to have any functionality that boils down to commands or event listeners accessible through an API. For the most part, that aim has been successful - there's a few bits and pieces that can be improved upon, but that will come with future updates too.

The API is also (mostly if I remember correctly) fully documented. If you want to check the individual classes, check the package on Github [here.](https://github.com/Niestrat99/AT-Rewritten/blob/v6/AdvancedTeleport-Bukkit/src/main/java/io/github/niestrat99/advancedteleport/api)

If you're not sure what I'm talking about and you're not a plugin developer - don't worry. Check the other pages :)&#x20;

## Dependency

To add the dependency, use the Modrinth Maven repository.

{% tabs %}
{% tab title="build.gradle.kts" %}
```kotlin
repositories {
    maven("https://api.modrinth.com/maven")
}

dependencies {
    compileOnly("maven.modrinth:advancedteleport:6.0.0")
}
```
{% endtab %}

{% tab title="build.gradle" %}

{% endtab %}

{% tab title="pom.xml (Maven)" %}

{% endtab %}
{% endtabs %}

`// TODO`

## Reference
