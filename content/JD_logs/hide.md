---
title: "No Player Export"
weight: 51
---

Using the export with no player details!

{{% notice info%}}
Since we’re not using player_id and player_2_id we have removed them from the export.
{{% /notice %}}

### Example: (/tweet [Message])

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