# Swift-DL

> [!CAUTION]  
> I doubt this works anymore, but if someone wants to submit a PR, please feel free to do so. This was more just for me to test the waters with Swift, but it could be useful for some. 

A macOS video/audio downloader. Think of it as a youtube downloader that works on many sites.

Swift-DL is a YT-DLP clone of the Youtube-DL GUI [_Get It_](https://github.com/Kevin-De-Koninck/Get-It) that includes additional bug fixes.

<img src="https://github.com/jslpc/Swift-DL/blob/master/ReadMe%20Resources/MainWindow.png?raw=true" height="400" /><img src="https://github.com/jslpc/Swift-DL/blob/master/ReadMe%20Resources/Settings.png?raw=true" height="400" />

**Note**: Swift-DL requires _Homebrew_. The required dependencies will be installed with _Homebrew_.

# TODO

- [ ] Add native dark mode with dynamic color scheme
- [ ] Full support for SponsorBlock

# Installation

Download it [here](https://github.com/jslpc/Swift-DL/releases/), unzip it and open it. When prompted, move it to the Applications folder.
To install the dependencies required to run the software, please open the settings in the app and click on 'Install/update software'. This will not update Swift-DL, but it will update all dependencies.

## Dependencies

### Install or Update

Swift-DL requires the following dependencies which you can install and/or update using the command line (see below).  
The following list is required:
- xcode-select
- brew
- python
- python3
- pycrypt
- yt-dlp
- libav
- ffmpeg

To install the dependencies, open the Terminal app and paste the following command to install and/or update the respective tools in one go.

``` bash
if ! xcode-select -v &> /dev/null; then xcode-select --install; fi; if brew -v &> /dev/null; then brew update; else echo /usr/bin/ruby -e '$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)'; fi; if brew ls --versions python &> /dev/null; then brew upgrade python; else brew install python; brew link python; fi; if brew ls --versions python3 &> /dev/null; then brew upgrade python3; else brew install python3; fi; if pip2.7 list | grep -i pycrypt &> /dev/null; then pip2.7 install pycrypt --upgrade; else pip2.7 install pycrypt; fi; if yt-dlp --version &> /dev/null; then brew upgrade yt-dlp; else brew install yt-dlp/taps/yt-dlp; fi; if brew list libav &> /dev/null; then brew upgrade libav; else brew install libav; fi; if brew list ffmpeg &> /dev/null; then brew upgrade ffmpeg; else brew install ffmpeg; fi
```

### Uninstall

To uninstall Swift-DL, simply trash the application from Finder.

Each component can be uninstalled **if** it is not used by another program on your Mac. To remove each separate dependency, run `brew uninstall [component]`, replacing `[component]` with the name of the dependency you no longer need.

To completely clean everything that is brew related:
https://github.com/Homebrew/install#uninstall-homebrew

To uninstall the developer tools:
``` bash
sudo rm -rf /Library/Developer/CommandLineTools
```

# About

Swift-DL will download audio and/or video from many websites such as YouTube, BBC, Instagram, and many more. It's a GUI built on the YT-DLP command-line tool, which is itself a fork of the popular program YouTube-DL, but with a clean and easy to use user interface.

It will save your settings dynamically or you can restore to the default settings. The default settings will download the audio from a video, convert it to an MP3 and save it to you downloads folder. This seems to be the most common use for using YT-DLP/YouTube-DL, though downloading the entire video is also supported in the settings pane.

# Common issues

Because this is a simple GUI wrapper for the `yt-dlp` command, most issues can be traced back to the binary. The can usually be resolved by simply updating YT-DLP as follows: `sudo yt-dlp --update`.

It is a known issue that sometimes you will see an error message that the download has failed. I'm working on a quick fix for this, but most of the time it completes the download perfectly. Be sure to check your Downloads folder for the audio/video file(s) to see if it actually worked properly before creating a new issue.

# Bug reports and feature requests

Use the [Issues](https://github.com/jslpc/Swift-DL/issues) page to submit any bug reports. Please provide all information requested from the _Bug report_ issue template.

If you have any suggestions or feature requests, use the _Feature requests_ issue template.

Feel free to ask any other questions that don't fit either template, but make sure to be as descriptive as possible to ensure the best answer.

# THANKS

The [youtube-dl](https://github.com/rg3/youtube-dl) authors for creating such an amazing tool.

The devs of [yt-dlp](https://github.com/yt-dlp/yt-dlp) for improving upon it and actively maintaining the fork that this program is built on.

[Get-It](https://github.com/Kevin-De-Koninck/Get-It) developer Kevin De Koninck for building the original app that Swift-DL was cloned from.
