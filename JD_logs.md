# JD_logs

![release](https://img.shields.io/github/release/Prefech/JD_logs.png)
![Last Commit](https://img.shields.io/github/last-commit/Prefech/JD_logs)
![License](https://img.shields.io/github/license/Prefech/JD_logs.png)
![Issues](https://img.shields.io/github/issues/Prefech/JD_logs.png)
![Contributors](https://img.shields.io/github/contributors/Prefech/JD_logs.png)
[![Discord](https://discordapp.com/api/guilds/721339695199682611/widget.png)](https://discord.gg/prefech)

[![JD_logs](https://i.gyazo.com/3894b03d4351bcb566ec85afc7f9b231.png)](https://github.com/Prefech/JD_logs)

## Requirements
- A Discord Server
- FXServer

## Optional
- Prefech_Notify

## Main Features
- Basic logs:
  - Chat Logs (Messages typed in chat)
  - Join Logs (When i player is connecting to the sever)
  - Leave Logs (When a player disconnects from the server)
  - Death Logs (When a player dies/get killed)
  - Shooting Logs (When a player fires a weapon)
  - Resource Logs (When a resouce get started/stopped)
- Screenshot Logs
- Namechange Logs
- Logs with or without embeds.
- Optional custom logs
  - Easy to add with the export.

## Commands
- `/logs [ID]`
  - Will show you thr recent 5 logs made for that user.
  - You can change what channels are kept in the log history.

## Download & Installation

1. Download the files
2. Put the JD_logs folder in the server resource directory
3. Add this to your `server.cfg`
```
ensure JD_logs
```

## Export

To create custom logs you will need to add the export to the event/function or command you want to log.  
This is in the resource you want to log

```lua
exports.JD_logs:createLog({
    EmbedMessage = "EMBED MESSAGE",
    color = "#FFFFFF",
    player_id = SERVER_ID_PLAYER_ONE,
    player_2_id = SERVER_ID_PLAYER_TWO,
    channel = "CHANNEL FROM WEBHOOKS CONFIG",
    screenshot = true
})
```

- **EmbedMessage:** This can be anything you want it to say.
  - You can even use variables in it as long as they contain a value.
- **color:** This can be a decimal color or a hexadecimal.
- **player_id:** This will be the server id of the first player.
  - If you don't have a first player you can remove this.
- **player_2_id:** This will be the server id of the second player.
  - If you don't have a second player you can remove this.
- **channel:** This will be the channel you have set in the `webhooks.json`
  - This is **NOT** a webhook url you have to place that in the webhooks.json
- **screenshot:** this can be either true or false it will add a screenshot to embeds
  - You need to have embeds enabled on the channel to see screenshots!

### Single Player

Using the export for one player!

- **player_id:** is the variable that is used for getting the player info.  
- **player_2_id:** isn't used and therefore we can remove it from the export.  

?> for server-side resources `player_id` will be `source` on client-side this will be `GetPlayerServerId(PlayerId())`  
*Keep in mind these might also change depending on the framework*


Example: (/me [Message])
```lua
RegisterCommand("me", function(source, args, rawCommand)
    TriggerClientEvent('chatMessage', -1, "ME | " .. GetPlayerName(source)..": "..rawCommand:gsub("me", ""), { 201, 201, 201 })
    exports.JD_logs:createLog({
        EmbedMessage = "ME | " .. GetPlayerName(source)..": "..rawCommand:gsub("me", ""),
        color = "#FFFFFF",
        player_id = source,
        channel = "me",
        screenshot = false
    })
end)
```

**EmbedMessage:** This will be the /me message in this case  
**player_id:** In this use it will be source  
**player_2_id:** Since there is one player we have removed it  
**color:** This can be any color you want  
**channel:** This will be linked to the webhook in the config.  
**screenshot:** This can be true if you want the embed to include a screenshot.  

### Dual Player

Using the export for two players!

- **player_id:** is the variable that is used for getting the player info.
- **player_2_id:** this will be the server id of the second player to get their info.

?> `player_2_id` will be a server variable that is the server id of the second player  
*Keep in mind these might also change depending on the framework*

Example: (/mention [PlayerID])
```lua
RegisterCommand("mention", function(source, args, rawCommand)
    TriggerClientEvent('chatMessage', -1, "Mention | " .. GetPlayerName(args[1]), { 201, 201, 201 })
    exports.JD_logs:createLog({
        EmbedMessage = "Mention | " .. GetPlayerName(args[1]),
        color = "#FFFFFF",
        player_id = source,
        player_2_id = args[1],
        channel = "mention",
        screenshot = false
    })
end)
```

**EmbedMessage:** This will be the /mention message in this case  
**player_id:** In this use it will be source  
**player_2_id:** Since there is one player we have removed it  
**color:** This can be any color you want  
**channel:** This will be linked to the webhook in the config.  
**screenshot:** This can be true if you want the embed to include a screenshot.  

### Hide Player Details

Using the export with no player details!

?> Since we're not using `player_id` and `player_2_id` we have removed them from the export.  

Example: (/tweet [Message])
```lua
RegisterCommand("tweet", function(source, args, rawCommand)
    TriggerClientEvent('chatMessage', -1, "Tweet | " .. GetPlayerName(source)..": "..rawCommand:gsub("tweet ", ""), { 201, 201, 201 })
    exports.JD_logs:createLog({
        EmbedMessage = "Tweet | " .. GetPlayerName(source)..": "..rawCommand:gsub("tweet ", ""),
        color = "#FFFFFF",
        channel = "tweet",
        screenshot = false
    })
end)
```

**EmbedMessage:** This will be the /tweet message in this case  
**player_id:** Since there is no players we have removed it  
**player_2_id:** Since there is no players we have removed it  
**color:** This can be any color you want  
**channel:** This will be linked to the webhook in the config.  
**screenshot:** This can be true if you want the embed to include a screenshot.  

## Embeds

Embeds can be disabled in the `webhooks.json`

Just set the embed to false and you won't get a ambed build.

?>If you disabled embeds the export will output the `EmbedMessage` as a normal message.

!> If you disable embeds on a channel you will **NOT** be able to include player details or screenshots.