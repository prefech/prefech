---
title: "Export"
weight: 50
---

To create custom logs you will need to add the export to the event/function or command you want to log.
This is in the resource you want to log

```lua
exports.Prefech_Notify:Notify({
  title = "AWSOME TITLE",
  message = "AWSOME MESSAGE",
  color = "#93CAED",
  icon = "fas fa-user",
  target = PLAYER_ID,
  timeout = 10
})
```  

- **title:** This is the title you want the notification to have.
  - You can even use variables in it as long as they contain a value.
- **message:** This is the message you want to show.
- **color:** This is a hexadecimal color.
- **icon:** This is a fontawe some icon https://fontawesome.com/v6.0/icons?m=free
- **target:** This will be the server id of the player you want to send the notification to.
- **timeout:** This will be the time the notification will be shown
  - This is in seconds.


{{% notice info%}}
The target is only needed when you’re using the export server side.
{{% /notice %}}
