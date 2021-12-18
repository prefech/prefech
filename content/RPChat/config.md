---
title: "Configuration"
weight: 46
---

### Configuration

After you have installed JD_logs you can open the config file and change the settings to your needs.
You will find the config file in the config folder.

When you just installed JD_logs your config should look like this:
```lua
Config = {}

Config.commands = {
    { command = "me", channel = "Me", username = true, logchannel = "chat", suggestion = { command = "Action message.", args = {{ name="Message", help="The action." }} } },
    { command = "tweet", channel = "Tweet", username = true, logchannel = "chat", suggestion = { command =  "Twitter message.", args = {{ name="Message", help="The message you want to tweet." }} } },
    { command = "annontweet", channel = "Tweet", username = false, logchannel = "chat", suggestion = { command =  "Twitter message.", args = {{ name="Message", help="The message you want to tweet." }} } },
    { command = "ooc", channel = "", username = true, logchannel = "chat", suggestion = { command =  "Out Of Character message.", args = {{ name="Message", help="Out Of Character message." }} } },
    { command = "announce", channel = "Announce", logchannel = "chat",  perms = "jd.staff" },
    { command = "clear", channel = "Staff", logchannel = "chat", perms = "jd.staff" }
}

Config.ChatModes = {
    Staff = {name = "Staff", color = "#FF0000", logchannel = "chat", perms = "jd.staff"},
    Tweet = {name = "Tweet", color = "#1DA1F2", logchannel = "chat"},
    Me = {name = "Me", color = "#3CB371", logchannel = "chat"}
}

Config.Channels = {
    { name = 'system', range = 'global', icon = 'fas fa-cog', color = '#FFA500'},
    { name = 'announce', range = 'global', icon = 'fas fa-bullhorn', color = '#8A2BE2'},
    { name = 'Me', range = 19.999, icon = 'fas fa-user', color = '#3CB371'},
    { name = 'Tweet', range = 'global', icon = 'fab fa-twitter', color = '#1DA1F2'},
    { name = 'Staff', range = 'global', icon = 'fas fa-shield-alt', color = '#B22222'},
    { name = '', range = 'global', icon = 'fas fa-globe-europe', color = '#808080'}
}

Config.Sounds = {
    system = true,
    announce = true
}

Config.TimeStamp = true
Config.DaylightSavingTime = true
```

## Config settings:

#### Commands
Input | Required/Optional | Usage |
--- | --- | --- |
command | yes | This will be the /command |
channel | yes | This will be the channel from Config.Channels the command will post to for the markdown. |
username | no | This can be either `true`, `false` or a custom string. |
logchannel | no | This is the channel name you have defined in `JD_logs/config/webhooks.json` |
suggestion | no | just like adding chat suggestions so people will know how to use the command. |

#### Chat Modes
Input | Required/Optional | Usage |
--- | --- | --- |
name | yes | this will be the mode name displayed in the chat bar. it will also be the name for the Channel in Config.Channels for how the markdown. |
color | yes | This will be the color used for the Mode name in chat. |
logchannel | no | since modes are also logged in the `chat` channel you can choose to make a second log in a different channel to keep it more organized. |
perms | no | if you add an ace permission here the user needs to have the permission to use the mode. |

#### Channels
Input | Required/Optional | Usage |
--- | --- | --- |
name | yes | the name for the channel to use in modes or commands. |
range | yes | this can either be a number or `global.|
icon | yes | this is an icon that will be displayed in front of the username. (https://fontawesome.com/v5.9/icons/)|
color | yes | this will be the coler added to the message.|