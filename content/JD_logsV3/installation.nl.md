---
title: "Installatie"
weight: 45
---

### Installatie

1. Download de nieuwste versie van github: https://github.com/prefech/JD_logsV3 (Klik op de clone knop en download vervolgens naar zip.)
2. Plaats de map JD_logsV3 in de resource map
    - Zorg ervoor dat u de map hernoemt naar **JD_logsV3**.
3. Hernoem de **example.config.json** naar **config.json** (Het bestand bevindt zich in de config map)
4. Maak een bot token en voeg deze toe aan de `config.json`
    - Ik weet niet zeker hoe ik een bot-token moet krijgen? [Hoe een bot-token te krijgen.](https://forum.prefech.com/d/12-how-to-get-a-discord-bot-token)
    - De bots moeten de volgende intents hebben ingeschakeld:
        - Presence Intent
        - Server Members Intent
        - Message Content Intent
5. Voeg dit toe aan je server.cfg
```
ensure JD_logsV3
```
5. Start de resource een keer en laat hem bouwen.
6. Ga naar je discord waar je de bot hebt uitgenodigd (*De server waar je de main logs wilt.*) rn gebruik get volgende command `!jdlogs setup`.
7. Start je server opnieuw op en je ziet de logs op je discord.

{{% notice info%}}
Als je daarna problemen hebt met installeren, kun je een ticket maken op onze discord en we helpen je graag verder: https://prefech.com/discord
{{% /notice %}}
