---
title: "Configuratie"
weight: 46
---

### Configuratie

Nadat u JD_logs hebt geïnstalleerd, kunt u het configuratiebestand openen en de instellingen naar wens wijzigen.
U vindt het configuratiebestand in de configuratiemap.

Als je JD_logs net hebt geïnstalleerd, zou je configuratie er als volgt uit moeten zien:
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

#### Configuratie-instellingen:

#### Basis instellingen.
Instelling | Standaardwaarde | Gebruik |
--- | --- | --- |
prefix | `!` | Dit is het voorvoegsel voor het gebruik van de bot-opdrachten. |
token | `""` | Dit is het bot-token om in te loggen op discord. [Hoe krijg je een bot-token?](https://forum.prefech.com/d/12-how-to-get-a-discord-bot-token) |

#### Ace permission instellingen.
Instelling | Standaardwaarde | Gebruik |
--- | --- | --- |
nameChangePerms | `"jd.staff"` | Dit is de ace permission die nodig is om de naamswijziging live in-game chat te zien. |
screenshotPerms | `"jd.staff"` | Dit is de ace permission die nodig is om `/screenshot [id]` te kunnen gebruiken. |

#### Aanvullende instellingen
Instelling | Standaardwaarde | Gebruik |
--- | --- | --- |
All Logs | `true` | Als dit is ingesteld op 'true', probeert de resource elk log dat is gemaakt naar hey `all` kanaal in de channels.json te verzenden. |
weaponLog | `true` | Met deze instelling kunt u schiet logs aan of uit zetten. |
damageLog | `true` |  Met deze instelling kunt u damage logs aan of uit zetten. |
deathLog | `true` |  Met deze instelling kunt u death logs aan of uit zetten. |


#### Details van de speler
Instelling | Standaardwaarde | Gebruik |
--- | --- | --- |
playerId | `true` | Als dit is ingesteld op true, wordt het server-ID van de speler weergegeven in de spelersdetails. |
steamId | `true` | Als dit is ingesteld op true, wordt de steam hex weergegeven in de spelersdetails. |
steamUrl | `true` | Als dit is ingesteld op true, wordt de Steam-profiel-URL weergegeven in de spelersdetails. |
discordId | `true` | Als dit is ingesteld op true, wordt de discord-ID weergegeven in de spelersdetails. |
license | `true` | Als dit is ingesteld op true, wordt de license identificatie van de spelerslicentie weergegeven in de spelersdetails. |
ip | `true` | Als dit is ingesteld op true, wordt het IP-adres van de speler weergegeven in de spelersdetails.  |
playerPing | `true` | Als dit is ingesteld op true, wordt de ping van de speler weergegeven in de spelersdetails.  |
postals | `true` | Als dit is ingesteld op true, wordt een post opgenomen in de insluitingen.
playerHealth | `true` | Als dit is ingesteld op true, wordt het gezondheidsniveau van de speler weergegeven in de spelersdetails.|
playerArmor | `true` | Als dit is ingesteld op true, wordt het pantserniveau van de speler weergegeven in de spelersdetails. |

#### Niet geregistreerde wapens
Instelling | Standaardwaarde | Gebruik |
--- | --- | --- |
WeaponsNotLogged | `["WEAPON_SNOWBALL", "WEAPON_FIREEXTINGUISHER", "WEAPON_PETROLCAN"]` | Deze wapens worden niet geregistreerd in het `shooting` logs kanaal. |

#### DiscordAcePerms
Instelling | Standaardwaarde | Gebruik |
--- | --- | --- |
DiscordRoleId | `"ROLEID": { "groups": [], "perms": []}` | Voeg permissions toe op basis van discord rollen.