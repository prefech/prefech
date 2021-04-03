---
title: "Old config options"
hidden: true
---

# (v1.2.2 and earlier) Old config info below

## Configuration options

vMenu comes with a few configuration options besides the full permissions-based configuration options.
These seperate options can be configured using **Convars**. Convars, for those who don't know what they are, are variables that are set inside the server.cfg file (can also be done in-game, but for vMenu you should probably set them up inside the server.cfg file before starting vMenu). These variables can then be accessed by resources for easy configuration.

## Available options

Here you will find a list of convars that can be set for vMenu. Note that you must set these variables **above** the `start vMenu` line inside your server.cfg file. The convars in the example below are shown with their default values, possible values are also listed.

## Example

This is how your server.cfg file could look like when you install vMenu.<br>
Check each option's possible values for more info on the value. some values need to be surrounded by `""` , others should _not_ be surrounded by those quotes.

``` yaml
# Execute permissions file
exec permissions.cfg

# Set vMenu options
set vMenuOptionName 1 # for entering numbers, don't use the "quotes"
set vMenuOptionName2 "valueString" # for entering string/text values, DO add the "quotes"

# Start vMenu
start vMenu
```

{{% notice tip %}}
All these configuration options on this page are OPTIONAL. You can leave them out just fine and it will use the default value.
{{% /notice %}}

|Convar|Default|Values|Description|
|---|---|---|---|
| `vMenuDisableTimeAndWeatherSync` | `"false"` | `"false"` or `"true"` |Setting this to `"true"` will disable all weather and time options in the menu, as well as the syncing of weather/time between players, this allows you to get another resource to do this instead of vMenu. Set it to `"false"` or don't set it at all to keep weather/time sync/options enabled.|
| `vMenuDisableDynamicWeather` | `"false"` | `"false"` or `"true"` |Setting this to `"true"` will disable dynamic weather changes by default. It can still be enabled in-game if players have permission to toggle it. Set it to `"false"` or don't set it at all to enable dynamic weather changes by default whenever you start the resource.|
| `vMenuToggleMenuKey` | `244` |Any valid [control ID][control].|Set this to any valid [control ID][control]) if you want to change the default key to toggle the menu (keyboard users only) from "M" to another key. 244 (default value) is the Interaction Menu (M) key.|
| `vMenuNoClipKey` | `289` |Any valid [control ID][control].|Same as above, use any valid [control ID][control] to change the NoClip toggle key from the default (F2/289) to another key.|
| `vMenuLogKickActions` | `"true"` | `"false"` or `"true"` |Setting this to `"true"` will log all kick actions taken by staff and output them to the `vmenu.log` file inside your vMenu resource folder. `"false"` will disable this.|
| `vMenuLogBanActions` | `"true"` | `"false"` or `"true"` |Setting this to `"true"` will log all ban actions taken by staff and output them to the `vmenu.log` file inside your vMenu resource folder. `"false"` will disable this.|
| `vMenuBanCheaters` | `"false"` | `"false"` or `"true"` |Setting this to `"true"` will automatically ban players that attempt to use cheats/hacks that execute vMenu events (even bans players that are normally excempt from being banned). Set this to `"false"` (default) to disable this.|

### Even more settings

There are also some settings that can be changed that are not using permissions or convars. These options can be found inside the `fxmanifest.lua` (previously `__resource.lua` ) file. The settings are explained in there and you shouldn't need to change them at all. Unless Vespura asks for them to be changed. They are mostly related to logging and debugging, so unless you want to get verbose logging and annoying tooltips in-game, I wouldn't recommend changing it if everything functions correctly.

--------

## Appreciate my work?

Consider supporting me on [<i class='fab fa-patreon'></i> Patreon](https://www.patreon.com/vespura)!

[control]: https://docs.fivem.net/game-references/controls/#controls
[integer]: https://en.wikipedia.org/wiki/Integer
