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
    EmbedMessage = "EMBED MESSAGE",
    player_id = SERVER_ID_PLAYER_ONE,
    player_2_id = SERVER_ID_PLAYER_TWO,
    channel = "CHANNEL FROM WEBHOOKS CONFIG",
    screenshot = true
})
```

- **EmbedMessage:** This can be anything you want it to say.
  - You can even use variables in it as long as they contain a value.
- **player_id:** This will be the server id of the first player.
  - If you don't have a first player you can remove this.
- **player_2_id:** This will be the server id of the second player.
  - If you don't have a second player you can remove this.
- **channel:** Will be pre filled out if you use the `!jdlogs create` command.
  - This links to the channel in the `channels.json` This is **NOT** the channel id or channel name but the name in the file.
- **screenshot:** this can be either true or false it will add a screenshot to embeds
  - You need to have embeds enabled on the channel to see screenshots!

{{% notice info%}}
Since making custom logs are depending on what you want to logs i can not give any examples other than some standalone commands.
{{% /notice %}}