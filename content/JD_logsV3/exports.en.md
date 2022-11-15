---
title: "Exports"
weight: 50
---

{{% notice danger%}}
To make custom logs you will need to have some coding knowledge!
We only provide the export we can not help you make use of it.

If you run into issues you can always open a ticket but there won't be guarantee that we can help.
{{% /notice %}}


To create custom logs you will need to add the export to the event/function or command you want to log.
This is in the resource you want to log
You can use the command `!jdlogs create` on your discord server to setup a custom logs channel.

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

- **EmbedMessage:** This can be anything you want it to say.
  - You can even use variables in it as long as they contain a value.
- **player_id:** This will be the server id of the first player.
  - If you don't have a first player you can remove this.
- **player_2_id:** This will be the server id of the second player.
  - If you don't have a second player you can remove this.
- **channel:** Will be pre filled out if you use the `!jdlogs create` command.
  - This links to the channel in the `channels.json` This can also be the channel id or a webhook url.
- **screenshot:** this can be either true or false it will add a screenshot of the first player to embeds
- **screenshot2:** this can be either true or false it will add a screenshot of the second player to embeds
  - You need to have embeds enabled on the channel to see screenshots!
- **title:** Set a custom title for this export only.
- **color:** Set a custom color for this export only.
-**icon:** Set a custom icon for this export only.

{{% notice warning%}}
Since making custom logs are depending on what you want to logs i can not give any examples other than some standalone commands.
{{% /notice %}}

## Using the export with no player details!

Since we’re not using player_id and player_2_id we have removed them from the export.

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

- **EmbedMessage:** This will be the /tweet message in this case  
- **player_id:** Since there is no players we have removed it  
- **player_2_id:** Since there is no players we have removed it  
- **color:** This can be any color you want  
- **channel:** This will be linked to the channel in the config.  

## Using the export for one player!

- **player_id:** is the variable that is used for getting the player info.  
- **player_2_id:** isn't used and therefore we can remove it from the export.  

for server-side resources `player_id` will be `source` on client-side this will be `GetPlayerServerId(PlayerId())`  
*Keep in mind these might also change depending on the framework*

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

- **EmbedMessage:** This will be the /me message in this case  
- **player_id:** In this use it will be source  
- **player_2_id:** Since there is one player we have removed it  
- **channel:** This will be linked to the channel in the config.  
- **screenshot:** This can be true if you want the embed to include a screenshot.  

## Using the export for two players!

- **player_id:** is the variable that is used for getting the player info.
- **player_2_id:** this will be the server id of the second player to get their info.

{{% notice info%}}
**player_2_id** will be a server variable that is the server id of the second player  
*Keep in mind these might also change depending on the framework*

{{% /notice %}}

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

- **EmbedMessage:** This will be the /mention message in this case  
- **player_id:** In this use it will be source  
- **player_2_id:** Since there is one player we have removed it  
- **channel:** This will be linked to the channel in the config.  
- **screenshot:** This can be true if you want the embed to include a screenshot.  