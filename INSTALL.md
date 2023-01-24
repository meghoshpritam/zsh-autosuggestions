# My Ubuntu 22.04 Desktop setup

I am using Ubuntu 22.04 LTS Gnome edition, you can download it from the official Ubuntu website [here](https://ubuntu.com/#download)

## Table of contents

* [Update System](#update)
* [Flatpak Installation](#flatpak)
* [Homebrew Installation](#homebrew)
* [Installing zsh and ohmyzsh](#zsh_and_ohmyzsh)
  * [Installing auto suggestions for zsh](#zsh_auto_suggestions)
* [Devlopment Tools](#development-tools)
  * [go-lang](#go-lang)
  * [hugo](#hugo)
  * [python3](#python3)
    * [miniconda](#miniconda)
    * [anaconda](#anaconda)
    * [Jupyter Lab](#jupyterlab)
    * [Jupyter Notebook](#jupyternotebook)
  * [java](#java)
  * [nvm](#nvm)
    * [nodejs](#nodejs)
    * [yarn](#yarn)
    * [pnpm](#pnpm)
  * [Lamp Stack](#lamp-stack)
  * [Docker](#docker)
  * [FiraCode](#firacode)
* [Application Software](#application-software)
* [Themes](#themes)
* [Uninstall](#uninstall)

## Update

Update the system

```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
```

## Flatpak

Install flatpak

```bash
# install flarpak
sudo apt-get install flatpak
# flatpak plugin for software store
sudo apt-get install -y gnome-software-plugin-flatpak
# adding  flathub repository
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

See the documentation of the detail [here](https://flatpak.org/setup/Ubuntu/)

## Homebrew

```bash
# requirments
sudo apt-get install build-essential curl file git
# installation
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
# then set the path, the instruction will be given to you when you run the installation command and its complete

```

The official Linux installation instruction [here](https://docs.brew.sh/Homebrew-on-Linux)

The official site is [here](https://brew.sh/)

## zsh_and_ohmyzsh

```bash
sudo apt-get install -y zsh curl git
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

[ohmyzsh official site](https://ohmyz.sh/)

### zsh_auto_suggestions

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# set zsh-autosuggestions plugin in zsh
# open .zshrc file with nano
nano ~/.zshrc
# add zsh-autosuggestions in plugins
plugins=(git zsh-autosuggestions)
# press ^o enter then ^x to exit

# load the zsh file changes
source ~/.zshrc
```

For details information's check the official repo [here](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh)

## Development-tools

### go-lang

installing go-lang using snap, check it [here](https://snapcraft.io/go)

```bash
sudo snap install go --classic
# or using brew
brew install go
```

### Hugo

installing hugo with snap check it [here](https://snapcraft.io/hugo), I am using the extended edition for sass support

```bash
sudo snap install hugo --channel=extended/stable
# or using brew
brew install hugo 
```

For more information about Hugo check the official site [here](https://gohugo.io/)

### python3

installing python 3

```bash
sudo apt-get install -y python3-pip
sudo apt-get install -y build-essential libssl-dev libffi-dev python3-dev
sudo apt-get install -y python3-venv
```

Check the Digital Ocean tutorial for more information [here](https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-programming-environment-on-an-ubuntu-20-04-server)

### miniconda

Install mini conda for python development

* download the miniconda `.sh` file form [here](https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh) or go to [this page](https://docs.conda.io/en/latest/miniconda.html#linux-installers) and download the script.

```bash
# add the exicution permission to the script
chmod +x Miniconda3-latest-Linux-x86_64.sh
# run the script and ans yes for the questions
./Miniconda3-latest-Linux-x86_64.sh
```

### anaconda

```bash
# install the packages
sudo apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6
```

Download the Anaconda installer from [here](https://www.anaconda.com/products/individual#linux)

```bash
cd ~/Downloads
chmod +x Anaconda3* 
./Anaconda3 # and hit tab key
# answer yes for all the prompt
# set conda path in zsh
source ~/anaconda3/bin/activate
conda init zsh
conda deactivate
# if you want to turn off autometic activation of conda bash then turn it off
conda config --set auto_activate_base false
```

### JupyterLab

JupyterLab is a web-based interactive development environment for Jupyter notebooks, code, and data.

```bash
# insall with conda if conda is install
conda install -c conda-forge jupyterlab
# or install with pip
pip install jupyterlab
# run jupyter lab
jupyter-lab
```

Check the official doc [here](https://jupyter.org/install.html)

### JupyterNotebook

The Jupyter Notebook is an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and narrative text.

```bash
# insall with conda if conda is install
conda install -c conda-forge notebook
# or install with pip
pip install notebook
# run jupyter notebook
jupyter notebook
```

Check the official doc [here](https://jupyter.org/install.html)

### Java

Install open JDK and open JRE

```bash
# open JRE
sudo apt-get install -y default-jre
# open JDK
sudo apt-get install -y default-jdk
```

Check the Digital Ocean tutorial for more information [here](https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-on-ubuntu-20-04#installing-the-default-jrejdk)

### nvm

Install node version manager

```bash
# install nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
# set nvm plugin in zsh
# open .zshrc file wiht nano
nano ~/.zshrc
# add nvm in plugins
plugins=(git nvm)
# press ^o enter then ^x to exit

# load the zsh file changes
source ~/.zshrc
```

For more information check the official repository [here](https://github.com/nvm-sh/nvm)

### nodejs

Install node version 14 with nvm

```bash
nvm i 14
```

For more uses see the official doc [here](https://github.com/nvm-sh/nvm#usage)

### yarn

Installing yarn with npm

```bash
npm i -g yarn
```
For more information see the official doc [here](https://yarnpkg.com/getting-started)

### pnpm

Installing pnpm with npm

```bash
npm i -g pnpm
```

For more information see the official doc [here](https://pnpm.io/installation)

### Lamp-stack

```bash
# install apache2
sudo apt-get install apache2
# allow apache with ufe firewall
sudo ufw allow in "Apache"
sudo ufw allow in "Apache Full"
# install mysql-server as a database
sudo apt-get install mysql-server
# add password to the database and press y (yes) for all the prompt
sudo mysql_secure_installation
# run mysql
sudo mysql
# exit from mysql
exit
# install php and php extensions
sudo apt-get install -y php libapache2-mod-php php-mysql
# additional php extensions if you want to use laravel
sudo apt-get install -y openssl php-common php-curl php-json php-mbstring php-mysql php-xml php-zip
```

For a details tutorial about LAMP stack check out the Digital Ocean tutorial [here](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-20-04)

### Composer

Install composer for managing application-level packages in PHP

```bash
# install the additional dependencies
sudo apt-get install -y php-cli unzip
# move to home directory
cd ~
# download composer
curl -sS https://getcomposer.org/installer -o composer-setup.php
# verify it
HASH=`curl -sS https://composer.github.io/installer.sig`
php -r "if (hash_file('SHA384', 'composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
# install composer globally
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
# test the composer
composer
```

For details information about installation check the Digital Ocean tutorial [here](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-composer-on-ubuntu-20-04)

To know more about composer check the official doc [here](https://getcomposer.org/doc/)

### Docker

Install docker using snap, check it [here](https://snapcraft.io/docker)

```bash
sudo snap install docker
```

For more information about docker check the official site [here](https://www.docker.com/)

Run docker without `sudo`, reference [here](https://github.com/docker-archive/docker-snap/issues/1)

### Firacode

Free monospaced font with programming ligatures. [Official Repository](https://github.com/tonsky/FiraCode)

```bash
# add repository
sudo add-apt-repository "deb http://archive.ubuntu.com/ubuntu $(lsb_release -sc) universe"
# update 
sudo apt-get update
# install fira code
sudo apt-get install -y fonts-firacode
```

For details, installation instruction check dev.to blog [here](https://dev.to/josuerodriguez98/installing-firacode-on-windows-and-ubuntu-1fn1)

## Application-software

| Application Name   | Application Description                                      | Install Command                                           |
| :----------------- | :----------------------------------------------------------- | :-------------------------------------------------------- |
| Tweak Tool         | Graphical interface for advanced GNOME 3 settings. [Official Site](https://wiki.gnome.org/Apps/Tweaks). [Repository](https://gitlab.gnome.org/GNOME/gnome-tweaks) | `sudo apt-get install gnome-tweak-tool`                   |
| Dconf Editor       | Viewer and editor of applications' internal settings. [Official Site](https://wiki.gnome.org/Apps/DconfEditor). [Repository](https://gitlab.gnome.org/GNOME/dconf-editor) | `sudo apt-get install -y dconf-editor`                    |
| Stacer             | System Optimizer & Monitoring. [Official Site](https://oguzhaninan.github.io/Stacer-Web/). [Repository](https://github.com/oguzhaninan/Stacer) | `sudo apt-get install stacer`                             |
| GIMP               | Photo editor. [Official Site](https://www.gimp.org/). [Flathub](https://flathub.org/apps/details/org.gimp.GIMP) | `flatpak install flathub org.gimp.GIMP`                   |
| VLC Player         | Medai Player. [Official Site](https://www.videolan.org/vlc/). [Flathub](https://flathub.org/apps/details/org.videolan.VLC). [Repository](https://github.com/videolan/vlc) | `flatpak install flathub org.videolan.VLC`                |
| Visual Studio Code | Code Editor. [Official Site](https://code.visualstudio.com/). [Flathub](https://flathub.org/apps/details/com.visualstudio.code). [Repository](https://github.com/Microsoft/vscode/) | `flatpak install flathub com.visualstudio.code`           |
| Telegram Desktop   | Medai Player. [Official Site](https://telegram.org/). [Flathub](https://flathub.org/apps/details/org.telegram.desktop). [Source Code](https://telegram.org/apps#source-code) | `flatpak install flathub org.telegram.desktop`            |
| Inkscape           | Vector graphics editor. [Official Site](https://inkscape.org/). [Flathub](https://flathub.org/apps/details/org.inkscape.Inkscape). [Repository](https://gitlab.com/inkscape/inkscape) | `flatpak install flathub org.inkscape.Inkscape`           |
| Obs Studio         | Live streaming and screen recording. [Official Site](https://obsproject.com/). [Flathub](https://flathub.org/apps/details/com.obsproject.Studio). [Repository](https://github.com/obsproject/obs-studio) | `flatpak install flathub com.obsproject.Studio`           |
| Flameshot          | Screenshot software. [Flathub](https://flathub.org/apps/details/org.flameshot.Flameshot). [Repository](https://github.com/flameshot-org/flameshot) | `flatpak install flathub org.flameshot.Flameshot`         |
| qBittorrent        | Vector graphics editor. [Official Site](https://www.qbittorrent.org/). [Flathub](https://flathub.org/apps/details/org.qbittorrent.qBittorrent). [Repository](https://github.com/qbittorrent/qBittorrent) | `flatpak install flathub org.qbittorrent.qBittorrent`     |
| Android Studio     | Official integrated development environment. [Official Site](https://developer.android.com/studio). [Flathub](https://flathub.org/apps/details/com.google.AndroidStudio) | `flatpak install flathub com.google.AndroidStudio`        |
| DBeaver Community  | SQL client software. [Official Site](https://dbeaver.io/). [Flathub](https://flathub.org/apps/details/io.dbeaver.DBeaverCommunity). [Repository](https://github.com/dbeaver/dbeaver) | `flatpak install flathub io.dbeaver.DBeaverCommunity`     |
| Postman            | Platform for API Development. [Official Site](https://www.postman.com/). [Flathub](https://flathub.org/apps/details/com.getpostman.Postman) | `flatpak install flathub com.getpostman.Postman`          |
| Draw.io            | Online diagramming website. [Official Site](https://app.diagrams.net/). [Flathub](https://flathub.org/apps/details/com.jgraph.drawio.desktop). [Repository](https://github.com/jgraph/drawio) | `flatpak install flathub com.jgraph.drawio.desktop`       |
| Gravit Designer    | Vector graphic design app. [Official Site](https://www.designer.io/en/). [Flathub](https://flathub.org/apps/details/io.designer.GravitDesigner) | `flatpak install flathub io.designer.GravitDesigner`      |
| Evince             | Document viewer. [Official Site](https://wiki.gnome.org/Apps/Evince). [Flathub](https://flathub.org/apps/details/org.gnome.Evince). [Repository](https://gitlab.gnome.org/GNOME/evince) | `flatpak install flathub org.gnome.Evince`                |
| Okular             | Universal document viewer. [Offical Site](https://okular.kde.org/). [Flathub](https://flathub.org/apps/details/org.kde.okular). [Repository](https://github.com/KDE/okular) | `flatpak install flathub org.kde.okular`                  |
| PyCharm Community  | Python IDE. [Official Site](https://www.jetbrains.com/pycharm/). [Flathub](https://flathub.org/apps/details/com.jetbrains.PyCharm-Community) | `flatpak install flathub com.jetbrains.PyCharm-Community` |
| Beekeeper Studio   | SQL Editor and Database Manager. [Official Site](https://www.beekeeperstudio.io/). [Snap](https://snapcraft.io/beekeeper-studio). [Repository](https://github.com/beekeeper-studio/beekeeper-studio) | `sudo snap install beekeeper-studio`                      |
| Xournal++          | Handwriting notetaking software. [Official Site](https://typora.io/). [Flathub](https://flathub.org/apps/details/com.github.xournalpp.xournalpp). [Repository](https://github.com/xournalpp/xournalpp) | `flatpak install flathub com.github.xournalpp.xournalpp`  |

### Visual Studio Code

Code editor. [Official Site](https://code.visualstudio.com/)

### Free Download Manger (FDM)

Download manager. [Official Site](https://www.freedownloadmanager.org/)

### Ulauncher

Application launcher. [Official Site](https://ulauncher.io/)

### Typora

Markdown editor. [Official Site](https://typora.io/)

```bash
wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -
sudo add-apt-repository 'deb https://typora.io/linux ./'
sudo apt-get update
sudo apt-get install typora
```

## Themes

* <https://www.gnome-look.org/p/1403328/>
* <https://www.pling.com/p/1405756/>
* <https://www.gnome-look.org/p/1411743/>

## grub theme

* <https://www.gnome-look.org/p/1414997/>

## shell extensions

* <https://extensions.gnome.org/>
* <https://extensions.gnome.org/extension/19/user-themes/>

## Uninstall

I am not playing any games so, I uninstall all the pre-install games that come with Ubuntu and I also uninstall `Transmission` because I will install `qBitTorrent`.

```bash
sudo apt-get remove aisleriot gnome-mahjongg gnome-mines gnome-sudoku transmission transmission-common transmission-gtk
sudo apt-get autoremove
```

### Uninstall Miniconda

```bash
rm -r ~/miniconda3/
```

For more information check [this](https://docs.anaconda.com/anaconda/install/uninstall/) or [that](https://stackoverflow.com/questions/29596350/how-to-uninstall-mini-conda-python)
