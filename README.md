# Grabbber
A YT-DLP fork of the Youtube-DL GUI _Get It_ by Kevin DeKoninck.

Very much a work in progress.

----

# Get It
A macOS video/audio downloader. Think of it as a youtube downloader that works on many sites.

<img src="https://github.com/Kevin-De-Koninck/Get-It/blob/master/ReadMe%20Resources/MainWindow.png?raw=true" height="400" /><img src="https://github.com/Kevin-De-Koninck/Get-It/blob/master/ReadMe%20Resources/Settings.png?raw=true" height="400" />

**Note**: Get It requires _Homebrew_. The required dependencies will be installed with _Homebrew_.

# Installation

Download it [here](https://github.com/jslpc/Grabbber/releases/), unzip it and open it.
To install the dependencies required to run the software, please open the settings in the app and click on 'Install/update software'. This will not update Get It, but it will update all dependencies.

## dependencies

### Install or Update

Get It requires the following dependencies which you can install and/or update using the command line (see below).  
The following list is required:
- xcode-select
- brew
- python
- python3
- pycrypt
- youtube-dl
- libav
- ffmpeg

To install the dependencies, open the Terminal app and paste the following commands to install and/or update the respective tools.

**xCode command line tools**
``` bash
if ! xcode-select -v &> /dev/null; then xcode-select --install; fi
``` 
**Homebrew**
``` bash
if brew -v &> /dev/null; then brew update; else echo /usr/bin/ruby -e '$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)'; fi
``` 
**Python**
``` bash
if brew ls --versions python &> /dev/null; then brew upgrade python; else brew install python; brew link python; fi
``` 
**Python 3**
``` bash
if brew ls --versions python3 &> /dev/null; then brew upgrade python3; else brew install python3; fi
``` 
**PyCrypt**
``` bash
if pip2.7 list | grep -i pycrypt &> /dev/null; then pip2.7 install pycrypt --upgrade; else pip2.7 install pycrypt; fi
``` 
**Youtube-dl**
``` bash
if youtube-dl --version &> /dev/null; then brew upgrade youtube-dl; else brew install youtube-dl; fi
``` 
**LibAV**
``` bash
if brew list libav &> /dev/null; then brew upgrade libav; else brew install libav; fi
``` 
**FFMPEG**
``` bash
if brew list ffmpeg &> /dev/null; then brew upgrade ffmpeg; else brew install ffmpeg; fi
```

### Uninstall

Each component can be installed **if** it is not used by another program on your Mac. To completely clean everything that is brew related:
https://github.com/Homebrew/install#uninstall-homebrew

To uninstall the developer tools:
``` bash
sudo rm -rf /Library/Developer/CommandLineTools
```

# About

Get It will download audio and/or movies from many websites such as YouTube, BBC, Instagram, ... It's a GUI round the popular YouTube-DL command-line program but with an easy to use interface.
It will save your settings dynamically or you can restore the default settings. The default settings will download the audio from a video, convert it to an MP3 and save it to you downloads folder. This was, in my opinion, the mostly used setting.


# Common issues

Because this is a simple GUI wrapper for the `youtube-dl` command, most issues can be traced back to the binary. The following common issues exists and can be solved easily:
- **'Something went wrong'**: An example can be found in [#25](https://github.com/Kevin-De-Koninck/Get-It/issues/25). The can usually be resolved by simply updating youtube-dl as follows: `sudo youtube-dl --update`.


# Submit a bug

You can submit a bug here on Github. Please provide the following:
- The URL(s) that you try to download.
- Your settings.

Also, open the Terminal app on your MacBook and issue the following command:
```
cat /tmp/getit_logs
```

Provide the output of the first command of you have an issue while installing the required software and provide the output of the second command of you have problems while downloading your URLs.

# THANKS

Thanks to [youtube-dl](https://github.com/rg3/youtube-dl) authors for creating such an amazing tool.
