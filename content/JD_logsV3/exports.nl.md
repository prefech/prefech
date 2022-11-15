---
title: "Exports"
weight: 50
---

{{% notice danger%}}
Om custom logs te maken, moet u enige codeerkennis hebben!
Wij verzorgen alleen de export wij kunnen u niet helpen er gebruik van te maken.

Als je tegen problemen aanloopt, kun je altijd een ticket openen, maar er is geen garantie dat we je kunnen helpen.
{{% /notice %}}

Om custom logs te maken, moet u de export toevoegen aan de event/function of command die u wilt loggen.
Dit staat in de resource die u wilt loggen
Je kunt het commando `!jdlogs create` op je discord-server gebruiken om een custom logs kanaal aan te maken.

```lua
exports.JD_logsV3:createLog({
  EmbedMessage = "Embed Message",
  player_id = SERVER_ID_PLAYER_ONE,
  player_2_id = SERVER_ID_PLAYER_TWO,
  channel = "Channel name from channels.json | Discord Channel ID | Discord Webhook URL",
  screenshot = true,
	screenshot_2 = true,
	title = 'Custom Title',
	color = '#A1A1A1',
	icon = '✅'
})
```

- **EmbedMessage:** Dit kan alles zijn wat je wilt zeggen.
  - Je kunt er zelfs variabelen in gebruiken, zolang ze maar een waarde bevatten.
- **player_id:** Dit wordt de server-id van de eerste speler.
  - Als je geen speler hebt, kun je deze verwijderen.
- **player_2_id:** Dit wordt de server-id van de tweede speler.
  - Als je geen tweede speler hebt, kun je deze verwijderen.
- **channel:** Wordt vooraf ingevuld als u de opdracht `!jdlogs create` gebruikt.
  - Dit linkt naar het kanaal in de `channels.json` Dit kan ook de channel id of een webhook url zijn.
- **screenshot:** dit kan true of false zijn, het zal een screenshot toevoegen van de eerste speler.
- **screenshot2:** dit kan true of galse zijn, het zal een screenshot toevoegen van de tweede speler.
- **titel:** Stel alleen voor deze export een aangepaste titel in.
- **color:** Stel alleen voor deze export een aangepaste kleur in.
-**icon:** Stel alleen voor deze export een aangepast pictogram in.

{{% notice warning%}}
Aangezien het maken van custom logs afhankelijk is van wat u wilt loggen, kan ik geen andere voorbeelden geven dan enkele standalone commands.
{{% /notice %}}

## De export gebruiken zonder spelersgegevens!

Omdat we player_id en player_2_id niet gebruiken, hebben we ze verwijderd uit de export.

### Example: (/tweet [Message])

```lua
RegisterCommand("tweet", function(source, args, rawCommand)
    TriggerClientEvent('chatMessage', -1, "Tweet | " .. GetPlayerName(source)..": "..rawCommand:gsub("tweet ", ""), { 201, 201, 201 })
    exports.JD_logsV3:createLog({
        EmbedMessage = "Tweet | " .. GetPlayerName(source)..": "..rawCommand:gsub("tweet ", ""),
        channel = "tweet",
        screenshot = false
    })
end)
```

- **EmbedMessage:** Dit is in dit geval het /tweet bericht
- **player_id:** Aangezien er geen spelers zijn, hebben we deze verwijderd
- **player_2_id:** Aangezien er geen spelers zijn, hebben we deze verwijderd
- **color:** Dit kan elke gewenste kleur zijn
- **channel:** Dit wordt gekoppeld aan het kanaal in de configuratie.

## De export gebruiken voor één speler!

- **player_id:** is de variabele die wordt gebruikt om de spelersinformatie te krijgen.
- **player_2_id:** wordt niet gebruikt en daarom kunnen we deze uit de export verwijderen.

voor resources aan de serverzijde is `player_id` `source` aan clientzijde is dit `GetPlayerServerId(PlayerId())`
*Houd er rekening mee dat deze ook kunnen veranderen, afhankelijk van het framework*

### Example: (/me [Message])
```lua
RegisterCommand("me", function(source, args, rawCommand)
    TriggerClientEvent('chatMessage', -1, "ME | " .. GetPlayerName(source)..": "..rawCommand:gsub("me", ""), { 201, 201, 201 })
    exports.JD_logsV3:createLog({
        EmbedMessage = "ME | " .. GetPlayerName(source)..": "..rawCommand:gsub("me", ""),
        player_id = source,
        channel = "me",
        screenshot = false
    })
end)
```

- **EmbedMessage:** Dit is in dit geval het /me-bericht
- **player_id:** Bij dit gebruik zal het de bron zijn
- **player_2_id:** Aangezien er één speler is, hebben we deze verwijderd
- **channel:** Dit wordt gekoppeld aan het kanaal in de configuratie.

## Using the export for two players!

- **player_id:** is de variabele die wordt gebruikt om de spelersinformatie te krijgen.
- **player_2_id:** dit is de server-id van de tweede speler die zijn info krijgt.

voor resources aan de serverzijde is `player_id` `source` aan clientzijde is dit `GetPlayerServerId(PlayerId())`
*Keep in mind these might also change depending on the framework*


### Example: (/mention [PlayerID])
```lua
RegisterCommand("mention", function(source, args, rawCommand)
    TriggerClientEvent('chatMessage', -1, "Mention | " .. GetPlayerName(args[1]), { 201, 201, 201 })
    exports.JD_logsV3:createLog({
        EmbedMessage = "Mention | " .. GetPlayerName(args[1]),
        player_id = source,
        player_2_id = args[1],
        channel = "mention",
        screenshot = false
    })
end)
```

- **EmbedMessage:** Dit zal in dit geval het /mention bericht zijn
- **player_id:** Bij dit gebruik zal het de source zijn
- **player_2_id:** En sinds the command gebruikt maakt van een server id van de tweede speler kunnen we die hiervoor gebruiken.
- **channel:** Dit wordt gekoppeld aan het kanaal in de configuratie.