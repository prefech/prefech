---
title: "Installation"
date: 2018-06-28T16:39:00+02:00
weight: 20
---

## Installing vs Updating

If you're updating vMenu, instead of installing it from scratch, you need to make sure that you REPLACE **ALL** files, **EXCEPT** your `permissions.cfg` and all files in the `vMenu/config/` folder!

{{% notice warning%}}
**IMPORTANT**: Before installing vMenu, make sure your **[FXServer artifacts](https://runtime.fivem.net/artifacts/fivem/)** are up to date. Yes update the server. Just do it. Don't be lazy and come crying if it doesn't work because you didn't update the server.
{{% /notice %}}

{{% notice warning%}}
**IMPORTANT**: If you're updating vMenu from any version below v3.3.0, and you want to keep your saved bans, please read the changelog for the update [here](https://github.com/TomGrobbe/vMenu/releases/tag/v3.3.0-pre).
{{% /notice %}}

## Installation steps
1. Go to the RELEASES page (on the GitHub repo), and download "vMenu-\<version\>.zip", or use the "Download vMenu" button on the left side of this page to automatically download the latest version.
2. Once you've got your zip file, extract the files and copy everything into `/resources/vMenu/` so that you end up with the `fxmanifest.lua` (previously `__resource.lua`) file right here: `/resources/vMenu/fxmanifest.lua`.
{{% notice note%}}
If you're trying to join the server, and it gives you an error saying "Could not load resource vMenu" or something similar, then make sure that you've installed vMenu inside `/resources/vMenu/` and NOT inside `/resources/vMenu/vMenu/`! Also note that the resource folder name **MUST** be called `vMenu` (Case Sensitive!!!) or the script will not work.
{{% /notice %}}
3. Now that you've got your files inside `/resources/vMenu/`, go into the `/resources/vMenu/config/` folder and move (or copy) the `permissions.cfg` file to the _same_ folder where your `server.cfg` file is located.
{{% notice tip%}}
If you're using ZAP Hosting, you might want to leave the permissions.cfg file inside the config folder, and use `exec resources/vMenu/config/permissions.cfg` instead of `exec permissions.cfg` in step 4.
<br><br>Alternatively, if you don't want to mess with any of these installation steps, install vMenu using their one-click installer! Don't have a FiveM server yet? Click [here](https://zap-hosting.com/vespura2) to get a server, and use the code `Vespura-a-3715` at checkout for a 10% discount!
{{% /notice %}}
4. Go to your `server.cfg` file, and add `exec permissions.cfg` at the _very top_ of the file (use the other command explained in step 3 if you're using Zap Hosting).
5. Now, add `start vMenu` somewhere inside your server.cfg file, position doesn't matter as long as it's _below_ the `exec permissions.cfg` line.
6. Save the server.cfg file and start your server. Once you're in, you should be able to access most menu's just fine without having to configure anything inside the permissions.cfg. This is because it is setup to have certain permissions for everyone by default, only administrator/moderator sensitive options have been removed from the default permissions file.

Congratulations, you've just installed vMenu in it's most basic, plug-and-play configuration.


* To learn more about the **configuration options** that vMenu has to offer, checkout the [Configuration](/vmenu/configuration/) page.
* To learn more on how to **setup the permissions.cfg file**, take a look at the [Permissions Reference](/vmenu/permissions-ref/) page.


## Support / Trouble Shooting
vMenu is no longer supported. Check the archived support channels in my [Discord](https://vespura.com/discord) server (don't ask for help in my Discord because you'll get permanently muted for your inability to read, the support channel is archived for a reason), or check the forum topic. Most issues can be found there or here on the docs.


## F.A.Q.
Checkout the [F.A.Q. page](/vmenu/faq/)..


## Easy installation using ZAP Hosting
If you don't want to install vMenu yourself, then get a ZAP Hosting FiveM server using the link below, and install vMenu through their 1-click installer! Don't forget to use the code `Vespura-a-3715` at checkout for a 10% discount!

**Click [here to get a FiveM server from ZAP Hosting](https://zap-hosting.com/vespura2) and use the one-click installer from the control panel.**

[![banner](https://zap-cdn.com/interface/_images/banner/gameserver/fivem-affiliate-banner-1006x180.png)](https://zap-hosting.com/vespura2)

## Appreciate my work?
Consider supporting me on [<i class='fab fa-patreon'></i> Patreon](https://www.patreon.com/vespura)!