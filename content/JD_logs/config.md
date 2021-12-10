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
    "allLogs": true,
    "postals": true,
    "weaponLog": true,
    "inlineField": true,

    "playerId": true,
    "steamId": true,
    "steamUrl": true,
    "discordId": true,
    "license": true,
    "license2": true,
    "ip": true,
    "playerPing": true,

    "Session": false,
    "PlayTime": false,
    "playerHealth": true,
    "playerArmor": true,
    "timestamp": true,

    "forceSteam": false,

    "nameChangePerms": "jd.staff",
    "logHistoryPerms": "jd.staff",
    "screenshotPerms": "jd.staff",
    "AntiCheatBypass": "jd.staff",

    "DiscordUpdateNotify": true,

    "userName": "Bot Username Here",
    "avatar": "https://via.placeholder.com/30x30",
    "communityName": "Community Name Here",
    "communityLogo": "https://via.placeholder.com/30x30",
    "footerText": "2020 - 2021 © Prefech",
    "footerIcon": "https://via.placeholder.com/30x30",

    "PrefechGlobalBans": true,
    "GlobalBanBypass": [],

    "WeaponsNotLogged": [
        "WEAPON_SNOWBALL",
        "WEAPON_FIREEXTINGUISHER"
    ]
```

#### Config settings:

#### Basic settings.
Setting | Default value | Usage |
--- | --- | --- |
allLogs | `true` | If this has been set to true the resource will try to send every single log made to the `all` channel in the webhooks.json |
postals | `true` | If this has been set to true a postal will be included in the embeds.  (This will only work if you have embeds enabled for the channel.) |
weaponLog | `true` | If this has been set to true the resource will try to send a log to the `shooting` channel in your webhooks.json for every time a player fires a weapon. |
inlineField | `true` | If this has been set to true the player info fields will be nmext to each other in the embed. When set to false they will be below each other. |

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

#### Additional player details
Setting | Default value | Usage |
--- | --- | --- |
Session | `false` | If this has been set to true the resource will try to get the players session time (Only works if you have Prefech_playerTime installed) |
PlayTime | `false` | If this has been set to true the resource will try to get the players total playtime (Only works if you have Prefech_playerTime installed) |
playerHealth | `true` | If this has been set to true the players health level will be displayed in the player details.  (Only shows when embeds are enabled for the channel.) |
playerArmor | `true` | If this has been set to true the players armor level will be displayed in the player details.  (Only shows when embeds are enabled for the channel.) |
timestamp | `true` | If this has been set to true the the timestamp of when the log was made will be added as a field..  (Only shows when embeds are enabled for the channel.) |

#### Steam usage settings.
Setting | Default value | Usage |
--- | --- | --- |
forceSteam | `false` | If this has been set to true player that not have steam activve will be kicked out and prompted to start their steam before they join back. |

#### Ace permission settings.
Setting | Default value | Usage |
--- | --- | --- |
nameChangePerms | `"jd.staff"` | This is the ace permission needed to see the name change live in-game chat. |
logHistoryPerms | `"jd.staff"` | This is the ace permission needed to use the `/logs [id]` command. |
screenshotPerms | `"jd.staff"` | This is the ace permission needed to use the `/screenshot [id]` command. |
AntiCheatBypass | `"jd.staff"` | This is the ace permission needed to bypass the anti cheat system that has been build into JD_logs |

#### Update Notifications
Setting | Default value | Usage |
--- | --- | --- |
DiscordUpdateNotify | `true` | If this has been set to true you will get notifications on resource updates in the `system` channel. (If no system channel has been defined in the webhooks.json it will be send to the `all` channel.) |

#### Cosmetic settings for embeds
Setting | Default value | Usage |
--- | --- | --- |
userName | `"Bot Username Here"` | This is the username that will be displayed on the webhook. |
avatar | `"https://via.placeholder.com/30x30"` | This will be the avatar the webhook will use. |
communityName | `"Community Name Here"` | This will be the name at the top of the embed. |
communityLogo  | `"https://via.placeholder.com/30x30"` | This will be the image at the top of the embed. |
footerText | `"2020 - 2021 © Prefech"` | This is the text that will get added to the footer of the embed. |
footerIcon | `"https://via.placeholder.com/30x30"` | This will be the icon at the footer of the embed. |

#### Prefech Global Bans
Setting | Default value | Usage |
--- | --- | --- |
PrefechGlobalBans | `true` | If this has been set to true people on the global ban list will be kicked of your server. |
GlobalBanBypass | `[]` | You can add any identifiers here for people that are global banned but you still allow them to play on your server. |

#### Not logged weapons
Setting | Default value | Usage |
--- | --- | --- |
WeaponsNotLogged | `["WEAPON_SNOWBALL", "WEAPON_FIREEXTINGUISHER"]` | These weapons will not be logged in the `shooting` channel. |
