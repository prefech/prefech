---
title: "One Player Export"
weight: 52
---

Using the export for one player!

- **player_id:** is the variable that is used for getting the player info.  
- **player_2_id:** isn't used and therefore we can remove it from the export.  

{{% notice info%}}
for server-side resources `player_id` will be `source` on client-side this will be `GetPlayerServerId(PlayerId())`  
*Keep in mind these might also change depending on the framework*
{{% /notice %}}


### Example: (/me [Message])
```lua
RegisterCommand("me", function(source, args, rawCommand)
    TriggerClientEvent('chatMessage', -1, "ME | " .. GetPlayerName(source)..": "..rawCommand:gsub("me", ""), { 201, 201, 201 })
    exports.JD_logs:createLog({
        EmbedMessage = "ME | " .. GetPlayerName(source)..": "..rawCommand:gsub("me", ""),
        player_id = source,
        channel = "me",
        screenshot = false
    })
end)
```

**EmbedMessage:** This will be the /me message in this case  
**player_id:** In this use it will be source  
**player_2_id:** Since there is one player we have removed it  
**channel:** This will be linked to the webhook in the config.  
**screenshot:** This can be true if you want the embed to include a screenshot.  
