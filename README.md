# Habbo-v31-Projector
Habbo v31 projector compatible with sso-ticket

## How to use the prebuilt projector

Copy the `dist` folder and change the vars.txt according this order:

- Your Habbo Server name, like `Habbo Hotel`
- `connection.info.host` value, like `retro.gabstep.com.br`
- `connection.info.port` value, like `40001`
- `connection.mus.host` value, like `retro.gabstep.com.br`
- `connection.mus.port` value, like `40002`
- `url.prefix` value, like `https://retro.gabstep.com.br
- `external.texts.txt` value, like `http://retro.gabstep.com.br:40000/dcr/v31/gamedata/external_texts.txt`
- `external.variables.txt` value, like `http://retro.gabstep.com.br:40000/dcr/v31/gamedata/external_variables.txt`
- DCR location, like `http://retro.gabstep.com.br:40000/dcr/v31/habbo.dcr`

## IMPORTANT!!
Your DCR and files like external.texts.txt, external.variables.txt, furnidata and productdata MUST BE served as HTTP (without SSL)
If you get random errors, try adding `?` after DCR location, external.texts.txt and external.variables.txt, because client can append some parameters to prevent caching.

Is strongly recommended to change your server `fuse_client.cct` to this `fuse_client.cct` (in dcr folder), to prevent browser opening in this client (conflicts in javascript calls);
This fuse_client will only do javascript calls if external variables contains `do.javascript.calls=true`.

## Recommendation
When we use a shockwave supported browser, we can play by browser. When we use a unsupported browser (recent browsers), we need to use this client.
The recommendation for supported browser is verify if the client supports shockwave. If no, instead of redirecting to /client_popup/install_shockwave or similar, show the `sso.ticket` client variable and instruct the user to copy and paste it to client.

## How to build

- Install Macromedia Director MX 2004.
- Double click src/projector.dir
- Edit what you want
- Press CTRL+SHIFT+S to build.

## Credits

Thank you https://github.com/Palsternakka/HabboLauncher for providing the base for this project.