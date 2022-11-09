---
title: "Configuration"
weight: 46
---

### Configuration

After you have installed JD_logs you can open the config file and change the settings to your needs.
You will find the config file in the config folder.

When you just installed JD_logs your config should look like this:
```json
{
    "prefix":"!jdlogs ",
    "token": "",
    "guildId": "",
    "TimezoneOffset": "+00:00",
    "language": "en",

    "NameChangePerms": "jd.staff",
    "screenshotPerms": "jd.staff",

    "allLogs": true,

    "weaponLog": true,
    "damageLog": true,
    "deathLog": true,

    "playerId": true,
    "postals": true,
    "playerHealth": true,
    "playerArmor": true,
    "playerPing": true,

    "ip": true,
    "steamUrl": true,
    "discordId": {
        "enabled": true,
        "spoiler": true
    },
    "steamId": {
        "enabled": true,
        "spoiler": true
    },
    "license": {
        "enabled": true,
        "spoiler": true
    },

    "WebhookResetMessage": false,

    "WeaponsNotLogged": [
        "WEAPON_SNOWBALL",
        "WEAPON_FIREEXTINGUISHER",
        "WEAPON_PETROLCAN"
    ],

    "DiscordAcePerms": {
        "DISCORD_ROLE_ID": {
            "groups": ["group.admin", "group.mod"],
            "perms": ["jd.staff"]
        }
    }
}
```

#### Config settings:

#### Basic settings.
Setting | Default value | Usage |
--- | --- | --- |
prefix | `!` | This is the prefix for using the bot commands. |
token | `""` | This is the bot token to login on discord. [How to get a bot token?](https://forum.prefech.com/d/12-how-to-get-a-discord-bot-token) |

#### Ace permission settings.
Setting | Default value | Usage |
--- | --- | --- |
nameChangePerms | `"jd.staff"` | This is the ace permission needed to see the name change live in-game chat. |
screenshotPerms | `"jd.staff"` | This is the ace permission needed to use the `/screenshot [id]` command. |

#### Additional settings
Setting | Default value | Usage |
--- | --- | --- |
All Logs | `true` | If this has been set to true the resource will try to send every single log made to the all channel in the channels.json |
weaponLog | `true` | With this setting you can enable or disable shooting logs. |
damageLog | `true` |  With this setting you can enable or disable damage logs. |
deathLog | `true` |  With this setting you can enable or disable death logs. |


#### Player details
Setting | Default value | Usage |
--- | --- | --- |
playerId | `true` | If this has been set to true the players server id will be displayed in the player details.  (Only shows when embeds are enabled for the channel.) |
steamId | `true` | If this has been set to true the steam hex will be displayed in the player details.  (Only shows when embeds are enabled for the channel.) |
steamUrl | `true` | If this has been set to true the steam profile url will be displayed in the player details.  (Only shows when embeds are enabled for the channel.) |
discordId | `true` | If this has been set to true the discord id will be displayed in the player details.  (Only shows when embeds are enabled for the channel.) |
license | `true` | If this has been set to true the players license identidier will be displayed in the player details.   (Only shows when embeds are enabled for the channel.) |
license2 | `true` | If this has been set to true the players license2 identidier will be displayed in the player details.  (Only shows when embeds are enabled for the channel.) |
ip | `true` | If this has been set to true the players ip will be displayed in the player details.  (Only shows when embeds are enabled for the channel.) |
playerPing | `true` | If this has been set to true the players ping will be displayed in the player details.  (Only shows when embeds are enabled for the channel.) |
postals | `true` | If this has been set to true a postal will be included in the embeds.
playerHealth | `true` | If this has been set to true the players health level will be displayed in the player details.|
playerArmor | `true` | If this has been set to true the players armor level will be displayed in the player details. |

#### Not logged weapons
Setting | Default value | Usage |
--- | --- | --- |
WeaponsNotLogged | `["WEAPON_SNOWBALL", "WEAPON_FIREEXTINGUISHER", "WEAPON_PETROLCAN"]` | These weapons will not be logged in the `shooting` channel. |

#### DiscordAcePerms
Setting | Default value | Usage |
--- | --- | --- |
DiscordRoleId | `"ROLEID": { "groups": [], "perms": []}` | Add permisions based on discord roles.