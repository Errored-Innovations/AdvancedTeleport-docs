# 📩 Custom Messages and Formats

AdvancedTeleport has a diverse and robust message handling system, of which provides a lot of control to the server administrator with how messages are sent and handled.

{% hint style="info" %}
As of v6, AdvancedTeleport will use MiniMessage as its primary messaging format, but will support legacy formatting for as long as it can.
{% endhint %}

## Normal and Multi-line Messages

Normal messages can simply be formatted as a string:

```yaml
  eventTeleport: '&b↑ &8» &7Teleporting...'
```

And that is that. Relatively straightforward.

If you want a message with multiple lines though, you can easily format them as a list:

```yaml
  eventTeleport:
  - '&b↑ &8» &7Teleporting...'
  - '&b↑ &8» &7Welcome to your destination!'
```

Or as a multi-line block:

```yaml
eventTeleport: |-
  &b↑ &8» &7Teleporting...
  &b↑ &8» &7Welcome to your destination!
```

If you use an apostrophe within a message surrounded by apostrophes, you can use them twice '' to cancel it out.

If you don't want a message to be sent at all, just make it empty:

```yaml
  eventTeleport: ''
```

Removing it will only re-add it since it is considered a required option in the config.

Like most plugins (to those who don't, why??), legacy colour formatting using &1, &2, etc. is supported in messages.

## Running Commands, Hoverable Text and Clickable Links

{% hint style="warning" %}
The format for this is being deprecated in v6 in favour of using the MiniMessage formatting. This still applies without issue for v5.
{% endhint %}

AdvancedTeleport uses a markdown format to allow clickable text to run commands and open links. This is demonstrated in the "TPA Request" received message - as a simple example:

<pre class="language-yaml"><code class="lang-yaml"><strong>  tpaRequestHere: '&#x26;b↑ &#x26;8» &#x26;7The player &#x26;b{player} &#x26;7wants to teleport you to them! [&#x26;aAccept](/tpayes {player}) [&#x26;cDeny](/tpano {player})'
</strong></code></pre>

The content within the square brackets is the only thing that appears, with the command in the normal brackets being hidden to the normal user. However, when the user clicks on the text, it will run the specified command.

If you want to add text you can hover over, then you will use the | divider to separate the command and text, similar to this:

```yaml
  tpaRequestHere: '&bTeleport Request &aYou &7-> &b{player} [&aAccept](/tpayes {player}|&aClick here to accept!|&7You want to accept, right?)'
```

Using the divider multiple times will split the hover text into multiple lines.

If you want to make text clickable to return a link instead, just insert the link into the normal brackets like you would with a command:

```yaml
  tpaRequestHere: 'Someone sent a TPA request but &b[here''s my boyfriend's twitter account instead](https://twitter.com/Niestrat99)'
```

## Titles and Subtitles

{% hint style="info" %}
Some older server versions do not support titles and subtitles whatsoever, and some do not support support fades in, duration or fades out.
{% endhint %}

By creating a new section with the \_title suffix, you can make titles appear when a message is sent - you may have seen this if you have used the plugin with its default settings.

`// TODO`

