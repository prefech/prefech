---
title: "Commands"
weight: 40
---

## Commands

### Game Commands
Name | Example | Usage
--- | --- | --- |
screenshot | /screenshot 12 | Will make a screenshot of the target player and send them to discord.|


### Discord Commands
Name | Example | Usage
--- | --- | --- |
setup | !jdlogs setup | Will run the setup for creating channels and adding them to the channels.json.|
create | !jdlogs create | Will run the setup to creat a export channel.|
delete | !jdlogs delete carrot | Will delete the channel carrot from the channels.json and the linked channel on discord.|
hide | !jdlogs hide screenshot ip | Will hide the ip from the screenshot logs.|
resethook | !jdlogs resethook | Will create a new webhook for imageStore. (Everytime JD_logsV3 starts the resource will create a new webhook just in case).|
players | !jdlogs players | Will return a list of online players and their server id.|
screenshot | !jdlogs screenshot 1 | Will create a screenshot of the player with server id 1.|
ss | !jdlogs ss 1 | Will create a screenshot of the player with server id 1 (Just a short command).|
uninstall | !jdlogs uninstall | Will remove all channels created by JD_logsV3 from the discord.