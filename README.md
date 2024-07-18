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
- `external.texts.txt` value, like `http://retro.gabstep.com.br:40000/dcr/v31/gamedata/external_texts.txt?`
- `external.variables.txt` value, like `http://retro.gabstep.com.br:40000/dcr/v31/gamedata/external_variables.txt?`
- DCR location, like `http://retro.gabstep.com.br:40000/dcr/v31/habbo.dcr`

### IMPORTANT!
external.texts.txt, external.variables.txt and DCR location MUST BE served as HTTP (without SSL)


## How to build

- Install Macromedia Director MX 2004.
- Double click src/projector.dir
- Edit what you want
- Press CTRL+SHIFT+S to build.

## Credits

Thank you https://github.com/Palsternakka/HabboLauncher for providing the base for this project.