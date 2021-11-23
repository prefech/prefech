---
title: "Two Player Export"
weight: 53
---

Using the export for two players!

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