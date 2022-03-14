# Development setup

| Setup             | March 2022                    |
|-------------------|-------------------------------|
| Hardware          | Apple MacBook Pro M1 2020     |
| CPU               | Apple M1                      |
| Memory            | 16GB                          |
| Disk              | 512GB                         |
| OS                | Apple macOS 12.2.1 (Monterey) |
| Screen resolution | 3360x2100 px                  |

## Software

### Karabiner Elements
Used for mapping keys, especially for polish accent characters (swapes right_option and right_command). Checkout file `karabiner.json`
<img width="1112" alt="image" src="https://user-images.githubusercontent.com/21008961/158254630-f96ffe88-54aa-430b-bce7-81b5540e0b18.png">


### Terminal
Terminal Emulator: iTerm2
Shell: ohmyzsh, `robbyrussell` theme
<img width="922" alt="image" src="https://user-images.githubusercontent.com/21008961/158258113-f72a0e19-fb3f-4a6a-ac21-1b77b115215a.png">

Useful aliases:
```bash
alias yt2mp3="youtube-dl --extract-audio --audio-format mp3"
alias yt2mp4="youtube-dl -f 'bestvideo[ext=mp4]+bestaudio[ext=m4a]/mp4'"

alias curltime="curl -w \"@$HOME/.curl-format.txt\" -o /dev/null -s "
alias curltime="curl -w \"@$HOME/.curl-format.txt\" -o /dev/null -s "
alias msq="mysql -u root -p -h 127.0.0.1"
```
Covid19 statistics:
```bash
curl covid19.mateuszwozniak.com
```
Tool `env2kube.sh` - tool for converting .env files to Kubernetes deployment env definitions
```python
#!/usr/bin/env python3
import sys

filename = sys.argv[1]

with open(filename) as file:
    lines = file.readlines()
    lines = [line.rstrip() for line in lines]
    for line in lines:
        if len(line) > 0:
            parts = line.split('=')
            if len(parts) > 1:
                if not parts[1].startswith('='):
                    parts[1] = '"' + parts[1] + '"'
                    print('- name: ' + parts[0])
                    print('  value: ' + parts[1])
```
Sample output:
```bash
$ env2kube .env
- name: APP_NAME
  value: "Laravel"
- name: APP_ENV
  value: "local"
- name: APP_KEY
  value: "base64:abcdefgh+iklkabdjsbdj"
- name: APP_DEBUG
  value: "true"
- name: APP_URL
  value: "http://localhost"
```

### FFMPEG
Awesome tool for working on video codecs

```bash
brew install ffmpeg
```
<img width="1090" alt="image" src="https://user-images.githubusercontent.com/21008961/158259441-be3dbc14-0ef0-4016-84a0-3e8becc108b7.png">
Some tips:


```bash

# Extract audio from mp4
ffmpeg -i input.mp4 -vn -acodec copy output-audio.aac

# Mute audio
ffmpeg -i input.mp4 -c copy -an output.mp4

# Reencode video with given CRF
ffmpeg -i input.mp4 -c:v libx264 -crf 18 -c:a copy output.mp4

# Trim video
ffmpeg -ss 00:01:00 -to 00:02:00 -i input.mp4 -c copy output.mp4

```

### Homebrew
Package manager

https://brew.sh/index_pl

### NVM - Node Version Manager
Easily switch Node.js versions

https://github.com/nvm-sh/nvm

```bash
nvm install 16
nvm use 16
```

### Alfred
Blazing fast spotlight alternative with many index features (checkout `main.alfredpreferences.zip` for importing config)

<img width="755" alt="image" src="https://user-images.githubusercontent.com/21008961/158256959-60e255a3-7c13-47fb-8a4b-e5b77c32d064.png">

Fallback searches can:
- search on YouTube
- search on Allegro
- calculate derivative
- calculate integral
- evaluate expression in Wolfram
- check person details in AGH SkOS
- search for song lyrics in Genius

Activation is using:


<img width="394" alt="image" src="https://user-images.githubusercontent.com/21008961/158257351-b27680b3-9a82-4551-8d21-c99842d8ccb3.png">


### Chrome - website browser

> Useful shortcuts:
> 
> `command + t` - new tab
> 
> `command + w` - close tab
> 
> `command + q` - exit chrome
> 
> `commnnd + 1,2,3,4...i` - switch to tab `i`

https://www.google.com/intl/pl_pl/chrome/


### HandBrake
Encoder for h264, h265. Useful for trimming videos or reencoding the codec. Can also rip DVDs

https://handbrake.fr/
<img width="1091" alt="image" src="https://user-images.githubusercontent.com/21008961/158256386-05d4698a-8fa9-4c6a-8dab-29d47fb45f1c.png">


### Tiles
Snaps windows to corners.

> Useful shortcuts
> 
> `option + command + left/right` - moves window to half of screen
> 
> `option + command + f` - fullscreen window

https://freemacsoft.net/tiles/
<img width="949" alt="image" src="https://user-images.githubusercontent.com/21008961/158254909-68ce4581-0225-410c-a033-58e6e4e5e81b.png">

### Motrix
Download manager, speeds up HTTP(s) downloads using concurrency

https://motrix.app/
<img width="934" alt="image" src="https://user-images.githubusercontent.com/21008961/158255300-6a009cfc-4183-46ef-b860-ccee9a52ba8c.png">

### VLC
Video player supporting many codecs

https://www.videolan.org/vlc/download-macosx.pl.html
<img width="884" alt="image" src="https://user-images.githubusercontent.com/21008961/158255532-29b9b4a5-213a-4d27-94ef-4ec37999abd1.png">

### GeoGebra Calculator Suite
Math toolkit for visualising things, especially useful in learning for exams

https://www.geogebra.org/download?lang=pl
<img width="1792" alt="image" src="https://user-images.githubusercontent.com/21008961/158256197-ed52960c-dd18-4528-a46c-582113882d5a.png">

