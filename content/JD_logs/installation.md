---
title: "Installation"
weight: 45
---
# Abandoned resource please use [JD_logsV3](../jd_logsv3/)

### Installation

1. Download the latest version from github: https://github.com/prefech/JD_logs/releases/latest
2. Put the JD_logs folder in the server resource directory
    - Make sure to remove the **-master** from the folder.
3. Add this to your server.cfg
```
ensure JD_logs
```
4. Navigate to the config file: **config/config.json**.
5. Update the settings in the config to your liking.
6. Navigate to the webhooks file: **config/webhooks.json**.
7. Add webhooks from discord and set the channel options to your liking
    - Not sure how to make a webhook have a look here: https://forum.prefech.com/d/17-creating-discord-webhooks
8. Restart your server and you should see the logs on your discord.

{{% notice info%}}
If you have any issues installing after this you can make a ticket on our discord and we're happy to help: https://discord.gg/prefech
{{% /notice %}}
