---
title: "Installation"
weight: 45
---

### Installation

1. Download the latest version from github: https://github.com/prefech/JD_logsV3 (Click the clone button and then download to zip.)
2. Put the JD_logsV3 folder in the server resource directory
    - Make sure to rename the folder to **JD_logsV3**.
3. Rename the **example.config.json** to **config.json** (The file is in the config folder)
4. Get yourself the bot token and add them in the `config.json`
    - Not sure how to get a bot token? [How to get a bot token.](https://forum.prefech.com/d/12-how-to-get-a-discord-bot-token)
    - The bots need to have the following intents enabled:
        - Presence Intent
        - Server Members Intent
        - Message Content Intent
5. Add this to your server.cfg
```
ensure JD_logsV3
```
5. Start the resource once and let it build.
6. Go to your discord where you invited the bot (*The one where you want your new main logs to be.*) and use the command `!jdlogs setup`.
7. Restart your server and you will see the logs on your discord.

{{% notice info%}}
If you have any issues installing after this you can make a ticket on our discord and we're happy to help: https://prefech.com/discord
{{% /notice %}}
