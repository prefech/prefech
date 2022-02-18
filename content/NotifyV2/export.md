---
title: "Export"
weight: 50
---

```lua
exports['Prefech_NotifyV2']:Notify({
    title = "SUCCESS",
    message = "You have been paid <span style='color:#47cf73'>$500</span>.",
    time = 5000,
    icon = "fas fa-credit-card",
    color = "#47CF73",
    target = PLAYER_ID
})
```

- **title:** This is the title you want the notification to have.
  - You can even use variables in it as long as they contain a value.
- **message:** This is the message you want to show.
- **time:** This will be the time the notification will be shown
  - This is in miliseconds.
- **icon:** This is a fontawe some icon https://fontawesome.com/v6.0/icons?m=free
- **color:** This is a hexadecimal color.
- **target:** This will be the server id of the player you want to send the notification to.


{{% notice info%}}
You can add a target server id both client and server side.
Even if the client is not the target.
{{% /notice %}}
