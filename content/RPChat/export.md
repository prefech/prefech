---
title: "Export"
weight: 50
---

The export will return a table with the player’s session time and the player’s total play time.
For example source is the player id and we want to check their time played on the server.
We will run the export in our function like this:
```lua
local playtime = exports.Prefech_PlayTime:getPlayTime(source)
```

Now the variable playtime will be a table.
The table will include both the session and total playtime.

- Session time in the table is named Session
- Total playtime in the table is named Total

The table returns the Total and Session playtime in seconds.

To get the playtime you simply have to grab the value from the table and check if it has been at least 5 minutes since they connected.
```lua
if playtime.Session >= 300 then
  print('They have been online for 5 minutes or longer')
else
  print('They have been online less than 5 minutes')
end
```

Now i used 300 since that is 5 minutes in seconds.
The export returns the playtime in seconds so you can convert it to minutes or hours.

Now to put it together our code will look like this:
```lua
local playtime = exports.Prefech_PlayTime:getPlayTime(source)
if playtime.Session >= 300 then
  print('They have been online for 5 minutes or longer')
else
  print('They have been online less than 5 minutes')
end
```


### Usage Examples
##### Client side total playtime example
```lua
RegisterNetEvent('PlayTimeCheck')
AddEventHandler('PlayTimeCheck', function()
    if exports.Prefech_PlayTime:getPlayTime(GetPlayerServerId(PlayerId())).Total >= 600 then
        return true
    else
        return false
    end
end)
```

##### Server side total playtime example
```lua
RegisterNetEvent('PlayTimeCheck')
AddEventHandler('PlayTimeCheck', function()
    if exports.Prefech_PlayTime:getPlayTime(source).Total >= 600 then
        return true
    else
        return false
    end
end)
```

##### Client side session playtime example
```lua
RegisterNetEvent('PlayTimeCheck')
AddEventHandler('PlayTimeCheck', function()
    if exports.Prefech_PlayTime:getPlayTime(GetPlayerServerId(PlayerId())).Session >= 600 then
        return true
    else
        return false
    end
end)
```

##### Server side session playtime example
```lua
RegisterNetEvent('PlayTimeCheck')
AddEventHandler('PlayTimeCheck', function()
    if exports.Prefech_PlayTime:getPlayTime(source).Session >= 600 then
        return true
    else
        return false
    end
end)
```