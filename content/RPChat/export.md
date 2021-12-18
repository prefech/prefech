---
title: "Export"
weight: 50
---

The exports work both client and server side.

### Hook into staff chat with another resource.
```lua
exports.Prefech_RPChat:TriggerMessage({ 
    type = 'Staff', 
    message = 'This is a staff message from a Server script.'
})
```
### Send System messaages from any resource.
```lua
exports.Prefech_RPChat:TriggerMessage({ 
    type = 'system', 
    message = 'This is a system message from a Server script.'
})
```
### Send announcements from any resource.
```lua
exports.Prefech_RPChat:TriggerMessage({ 
    type = 'announce', 
    message = 'This is a system message from a Server script.'
})
```

### Custom messages in chat.
```lua
exports.Prefech_RPChat:CustomTriggerMessage({ 
    target = source,
    message = 'JokeDevil has been transported to the Hospital.',
    icon = 'fas fa-ambulance',
    color = '190, 213, 90',
    name = 'Ambulance'
})
```