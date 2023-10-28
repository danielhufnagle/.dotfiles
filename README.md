# .dotfiles

These are my dotfiles for MacOS, running on a 14 inch M2Pro macbook pro

Your mileage may vary.

## Requirements
[Homebrew](https://brew.sh/) - this is how we will install most of this software, homebrew is a package manager for MacOS

[yabai](https://github.com/koekeishiya/yabai) - this is what we will use as our tiling window manager

[skhd](https://github.com/koekeishiya/skhd) - this is the keyboard shortcut daemon we will be using

[Oh My Zsh](https://ohmyz.sh/#install) - this is how we will theme our terminal and make it look pretty (The "fuhd" theme used in this configuration is a modified version of the agnoster oh-my-zsh theme)

[Neofetch](https://github.com/dylanaraps/neofetch) - this is not strictly necessary, but I like it

[Roboto Mono Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.0.2/RobotoMono.zip) - this is the font that I use for basically everything, installing this font (or any other nerd font) is needed for the zsh theme (as well as a lot of other nice utilities (such as neovim plugins)) to work

#### Other good information to know beforehand
The theme that I use for just about everything is called ["Nord"](https://www.nordtheme.com/). I like the clean dark blue and subdued colors offered. Nord is a theme that is found basically everywhere from programmer tools like VSCode, Neovim (with plugins like NVChad), RStudio, to more common applications like Spotify (tweaked with Spicetify), Discord (tweaked with BetterDiscord), Obsidian, and most themeable browsers (Firefox, Chrome, etc.)

I'm not including customizations color schemes simply because all the customization actually done through dotfiles is for yabai, skhd, and zsh. Theme things yourself.

Other popular themes are [Catpuccin](https://github.com/catppuccin/catppuccin), [Tokyo Night](https://github.com/enkia/tokyo-night-vscode-theme), [Dracula](https://draculatheme.com/), [Solarized](https://ethanschoonover.com/solarized/), [Gruvbox](https://github.com/morhetz/gruvbox)

## Other tools/apps that show up in my setup
[Spicetify](https://spicetify.app/) - allows for spotify tweaking and theming

[BetterDiscord](https://betterdiscord.app/) - allows for discord tweaking and theming

[iterm2](https://iterm2.com/) - a terminal emulator that has quite a bit more customizability than the default MacOS terminal

## Usage
Windows will automatically tile in a binary space partitioning layout

#### Keyboard shortcuts
(note that alt means option)

ctrl + alt - up: mirror across the x-axis

ctrl + alt - down: mirror across the y-axis

ctrl + alt - right: rotate layout by 270 degrees

ctrl + alt - left: rotate layout by 90 degrees

ctrl + alt - a: move window to next display to the left

ctrl + alt - d: move window to the next display to the right

ctrl + alt - t: free window from tiling

ctrl + alt - i: swap window with the one above it

ctrl + alt - k: swap window with the one below it

ctrl + alt - j: swap window with the one to the left of it

ctrl + alt - l: swap window with the one to the right of it

fn + left click and drag: swap windows with the one in the direction of the drag (this does not work with a mouse)

fn + right click and drag: resize window in the direction of the drag (if using a mouse this action gets remapped to fn + left click and drag)

#### Making an app not tile
From the home folder go to ```.config/yabai``` and open ```yabairc```. At the bottom you can see all the apps that have their tiling disabled by default. Copy this format when adding an app to disable from tiling

## Install (for complete beginners)
#### Clone the repository
Clone this repository into your home folder by opening a terminal (press command and space to open spotlight and then type terminal then enter) and paste and enter the following command:
```
git clone https://github.com/danielhufnagle/.dotfiles.git
```
We now have this repository as a folder in our home folder.

Next, let's install all the utilities that we need.

#### Install homebrew
While still in the terminal, paste and enter the following command:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Proceed by entering your password wherever it prompts you and hitting enter whenever it asks. (Don't worry this is completely safe. If you are asked for your password or to hit enter or y later on at any point in this tutorial, do it)

This will install homebrew. If you are on an M-series Mac you will get some message along the lines of:
```
==> Next steps:
- Run these two commands in your terminal to add Homebrew to your PATH:
    echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/yourusername/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"
- Run brew help to get started
- Further documentation:
    https://docs.brew.sh
```
This means that homebrew hasn't been added to our path so we can't use it. We can fix it by pasting and then entering the two lines below one at a time
```
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
```
```
eval "$(/opt/homebrew/bin/brew shellenv)"
```
This will add Homebrew to our PATH so that we can use it to install everything else we need
#### Install yabai and skhd
Still in the terminal, let's now install yabai and skhd
Paste and enter the following commands
```
brew install koekeishiya/formulae/yabai
```
```
brew install koekeishiya/formulae/skhd
```

#### Install neofetch
Paste and enter in the following command
```
brew install neofetch
```

#### Install Oh My Zsh
Assuming your Mac is relatively up to date we can just paste and enter the command below to install Oh My Zsh
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
I would advise against closing your terminal as we will need it later

#### Install Roboto Mono
Go to the link to the download for the font [https://github.com/ryanoasis/nerd-fonts/releases/download/v3.0.2/RobotoMono.zip](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.0.2/RobotoMono.zip) and download the font. Go to the ```Downloads``` folder in Finder and double click the zip file to extract it. Go into the newly created ```RobotoMono``` folder. 

From here select all the .ttf files and right click and select open. This will install Roboto Mono. 

#### Installing the configuration
Then open Finder and then press command shift H to go to your home folder. I would recommend pinning this folder somewhere to your favorites because of how important this folder is.

From there press command shit . (period) to show your hidden files. Now we can see that there are a lot more files, almost all of which start with a .

This includes the ```.dotfiles``` folder that we got earlier. From here you may want to open a few more Finder windows to your home folder and make sure that the hidden files are visible

Open the ```.config``` folder in one of your Finder windows and the ```.dotfiles``` folder in another.

Drag and drop the ```yabai``` and ```skhd``` folders from ```.dotfiles``` into ```.config```. We have now imported our configuration files for these two pieces of software.

Next, open the ```zsh``` folder in ```.dotfiles```. Inside ```zsh``` there should be two files, one called ```.zshrc``` and another called ```fuhd.zsh-theme``` If there are not, hit command shift . (period) to show hidden files and ```.zshrc``` will now be visible.

Drag and drop the ```.zshrc``` file into the home folder, opting to replace the previous ```.zshrc``` file. If you want to keep your old ```.zshrc``` file, I would recommend renaming the old file to something else. From inside your home folder, go into ```.oh-my-zsh``` and then into ```themes```. This is where you drag and drop the ```fuhd.zsh-theme``` file

#### Getting everythiung up and running
In your terminal paste and enter the following commands
```
source ~/.zshrc
```
This will "refresh" your terminal and you should see a rainbow apple in your terminal.
```
yabai --start-service
```
```
skhd --start-service
```
The above commands will start yabai and skhd

