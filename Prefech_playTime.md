# PlayTime

![release](https://img.shields.io/github/release/Prefech/Prefech_playTime.png)
![Last Commit](https://img.shields.io/github/last-commit/Prefech/Prefech_playTime)
![License](https://img.shields.io/github/license/Prefech/Prefech_playTime.png)
![Issues](https://img.shields.io/github/issues/Prefech/Prefech_playTime.png)
![Contributors](https://img.shields.io/github/contributors/Prefech/Prefech_playTime.png)
[![Discord](https://discordapp.com/api/guilds/721339695199682611/widget.png)](https://discord.gg/prefech)

## Requirements
- FXServer

## Main Features
- Saves the playtime of every player
- External acessable info you can use on your website! (SERVER_IP:PORT/Prefech_playTime/info)
- Export function to get the total play time and current session time in any resource you need it.
  - Export will return a table with the values in seconds.
  - `exports.Prefech_PlayTime:getPlayTime(PLAYER_ID)`
  - want to give players access to certain things after being x amount of time online. you can simpliy check with the export if you have played long enough!

## Commands
- `/getPlayTime [PlayerID]`
  - The player ID is optional it will return your own playtime if you don't include it.

# Download & Installation
1. Download the files
2. Put the Prefech_PlayTime folder in the server resource directory
3. Add this to your `server.cfg`
```
ensure Prefech_PlayTime
```

## Export
The export will return a table with the player's session time and the player's total play time.  
For example source is the player id and we want to check their time played on the server.  
We will run the export in our function like this:  
```lua
local playtime = exports.Prefech_PlayTime:getPlayTime(source)
```
Now the variable `playtime` will be a table.  
The table will include both the session and total playtime.  
- Session time in the table is named `Session`
- Total playtime in the table is named `Total`

?> The table returns the Total and Session playtime in seconds.  

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


## Usage Examples

#### Client side total playtime example
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

#### Server side total playtime example
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

#### Client side session playtime example
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

#### Server side session playtime example
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