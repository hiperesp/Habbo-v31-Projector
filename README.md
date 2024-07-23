# Habbo-v31-Projector
Habbo v31 projector compatible with sso-ticket

## How to use the prebuilt projector

Download the [latest release](https://github.com/hiperesp/Habbo-v31-Projector/releases) folder follow this:

### Full dynamic client (with custom ticket prompt)

If you want your users to connect with dynamic sw1...sw9 variables and dcr, with working following room and other features, just download the release and distribute it. You only need to create custom ticket in your client_install_shockwave.tpl following this:

`sw1|sw2|sw3|sw4|sw5|sw6|sw7|sw8|sw9|dcr_url`, replacing sw1...sw9 by your sw1...sw9 values provided in your client, and dcr_url must be your habbo.dcr location.
If you want custom sizes, append `|960|540` in your string, changing 960 by the width and 540 by the height.
This is the ticket you will send to your users through client_install_shockwave.tpl or client.tpl.

### Normal client (with normal ticket prompt)

You need to download the release and create a vars.txt like that:

- Line 1 - 9: must be your sw1...sw9 values. If is no sw9 or any other sw, let the line empty.
- Line 10: must be your habbo.dcr location.
- Line 11: is the sso ticket obligatoriness. 0 = no prompt, login by client. 1 = always prompt by normal sso ticket, 2 = optional. will be prompted, but you can let it empty.
- Line 12: the /client url
- Line 13 (optional): client width
- Line 14 (optional): client height

If you want, you can copy vars.example.txt to vars.txt and modify it too.

### Normal client (without prompt)

Follow the "Normal client (with normal ticket prompt)" instructions, but let the sso ticket obligatoriness 0.

## IMPORTANT!!
Your DCR and files like external.texts.txt, external.variables.txt, furnidata and productdata MUST BE served as HTTP (without SSL)
If you get random errors, try adding `?` after DCR location, external.texts.txt and external.variables.txt, because some clients can append some parameters to prevent caching.

Is strongly recommended to change your server `fuse_client.cct` to this `fuse_client.cct` (in dcr folder), to prevent browser opening in this client (conflicts in javascript calls);
This fuse_client will only do javascript calls if external variables contains `do.javascript.calls=true`.

## Web fix
When we use a shockwave supported browser, we can play by browser. When we use a unsupported browser (recent browsers), we need to use this client.
The recommendation for supported browser is verify if the client supports shockwave. If no, we show the `sso.ticket` client variable and instruct the user to copy and paste it to client.

You can do it by replacing the `www/client.tpl` with the file in `www` folder.

If you usethe full dynamic client, you can use the `www/client_install_shockwave-dynamic.tpl` file in this repository to replace the `client_install_shockwave.tpl` file in `www` folder.

If you use sso ticket obligatoriness = 0, you can use the `www/client_install_shockwave-0.tpl` file in this repository to replace the `client_install_shockwave.tpl` file in `www` folder.

If you use sso ticket obligatoriness = 1, you can use the `www/client_install_shockwave-1.tpl` file in this repository to replace the `client_install_shockwave.tpl` file in `www` folder.

If you use sso ticket obligatoriness = 2, you can use the `www/client_install_shockwave-2.tpl` file in this repository to replace the `client_install_shockwave.tpl` file in `www` folder.

We use sessionStorage to store the `sso.ticket` in `client.tpl` and we show it in `client_install_shockwave.tpl`.


## How to build

- Install Macromedia Director MX 2004.
- Double click src/projector.dir
- Edit what you want
- Press CTRL+SHIFT+S to build.

## More!

### How to create a Mac OS Launcher?
You need to install the app creator (wineskin) and create a software based on you launcher files.

To install the app creator (wineskin) following the instructions on https://github.com/Gcenx/WineskinServer

After install the app creator, follow this video steps https://www.youtube.com/watch?v=6VSGvNfb-OQ

When the "Choose Setup Executable" screen appears, use the "Copy a Folder Inside" or ""Move a Folder Inside" and select your unzipped launcher folder.

## Credits

Thank you https://github.com/Palsternakka/HabboLauncher for providing the base for this project.
