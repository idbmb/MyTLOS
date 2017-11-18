# MyTLOS
Repository for help me installing some important tools on my laptop, based on **TeaLinuxOS 8.1 Peppermint 64-bit** Build on Ubuntu 16.04 - http://tealinuxos.org/

## Desktop Setting
**[optional theme]**

`sudo sh -c "echo 'deb http://download.opensuse.org/repositories/home:/Horst3180/xUbuntu_16.04/ /' > /etc/apt/sources.list.d/arc-theme.list"`

`sudo apt-get update`

`sudo apt-get install arc-theme`

`setting --> appearance --> Arc-Darker`

> **Note :** *Do With Your Own Risk*
>
>**[used themes]**
[macOS-Sierra](https://github.com/B00merang-Project/macOS-Sierra)
>
>**[used icons]**
[la-capitaine-icon-theme](https://github.com/keeferrourke/la-capitaine-icon-theme)
>
>`cp -r` copy directory along the entire file contents
>
>change the background (oke.png its my background filename) :
>
>`sudo cp /home/bambang/Pictures/Wallpapers/oke.png /usr/share/xfce4/backdrops/`

**Dock**

*Installing cairo-dock available at **software center**.*

remove the line above dock (cairo-dock)

`settings --> window manager tweaks --> compositor`

**uncheck :** *Show shadows under dock windows*

**Auto Start on startup**

Settings --> Session and startup --> Application Autostart --> (+) Add

```
Name: Cairo Dock Start
Description : Autostart cairo-dock
Command: cairo-dock &
```

------

## Application

**BROWSER**

Default Browser TeaLinuxOS [Firefox Developer Edition](https://www.mozilla.org/en-US/firefox/developer/)

If you want used [Google Chrome](https://www.google.com/chrome/browser/desktop/index.html)

Chrome's download "Show in Folder" does not pop up folder
This time, Google did not manage to help me

Is it normal for nautilus not to pop up on the screen when I click "Show in Folder" in Chrome?

The folder did open but stay at a launcher, is it possible to make it pop up on my screen? with highlights if possible ..

**[Solved]** Open your terminal Just Press **F12** in TeaLinuxOS

`mimeopen -d /home/bambang/Downloads/`

```
Please choose a default application for files of type inode/directory

	1) Files  (nautilus-folder-handler)
	2) Audacious  (audacious)
	3) Open Folder with Thunar  (Thunar-folder-handler)
	4) Files  (org.gnome.Nautilus)
	5) Other...

use application# 1

```
*at use application# enter 1 Its a Files  (nautilus-folder-handler)*

------

**MUSIC**

[Spotify for linux](https://www.spotify.com/id/download/linux/)

```
# 1. Add the Spotify repository signing key to be able to verify downloaded packages
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys BBEBDCB318AD50EC6865090613B00F1FD2C19886

# 2. Add the Spotify repository
echo deb http://repository.spotify.com stable non-free | sudo tee /etc/apt/sources.list.d/spotify.list

# 3. Update list of available packages
sudo apt-get update

# 4. Install Spotify
sudo apt-get install spotify-client

```
------

**SOCIAL MEDIA**

**Slack Desktop**

https://slack.com/downloads/linux

**Telegram Desktop**

https://desktop.telegram.org/

------

**OFFICES**

The default apps offices in TeaLinuxOS LibreOffices but i dont like this, So I'm Uninstall it.

```
sudo apt-get remove --purge libreoffice*
sudo apt-get clean
sudo apt-get autoremove

```

i'm used WPS Offices

http://wps-community.org/downloads

### Etc

**gscan2pdf**

gscan2pdf can control regular or sheet-fed (ADF) scanners with SANE via libsane-perl, scanimage or scanadf, and can scan multiple pages at once. It presents a thumbnail view of scanned pages, and permits simple operations such as cropping, rotating and deleting pages.

**To Convert PDF To JPG**

Open Terminal

`convert -density 300 file.pdf file.jpg`

**How To Screenshot My Login Screen**

TAKE SCREENSHOT OF LOGIN SCREEN IN **TeaLinuxOS**

Create a new file, preferably in your Home directory. Name it **screenshot.sh** or anything you like. Add the following lines in this file:

```
chvt 7; sleep 5s; DISPLAY=:0 XAUTHORITY=/var/run/lightdm/root/:0 xwd -root -out ~/screenshot.xwd; convert ~/screenshot.xwd ~/screenshot.png; rm ~/screenshot.xwd

```
You must give the script execution rights:

`sudo chmod +x screenshot.sh`

Now when everything is ready, log out of the system. Press Ctrl+Alt+F1 at the login screen to go console mode. Login with your user credential. Run the screenshot script like this:

`sudo ./screenshot.sh`

Once the script is run, it will take you back to login screen graphical interface (chvt 7) and after five seconds it will take and save the screenshot in your home directory with a file name screenshot.png.

[References](https://itsfoss.com/screenshot-login-screen-ubuntu-linux/)


**Google Earth**

`cd /tmp
mkdir google-earth && cd google-earth
wget http://archive.ubuntu.com/ubuntu/pool/main/l/lsb/lsb-invalid-mta_4.1+Debian11ubuntu8_all.deb
wget http://archive.ubuntu.com/ubuntu/pool/main/l/lsb/lsb-security_4.1+Debian11ubuntu8_amd64.deb
wget http://archive.ubuntu.com/ubuntu/pool/main/l/lsb/lsb-core_4.1+Debian11ubuntu8_amd64.deb
sudo dpkg -i *.deb
sudo apt -f install`


`sudo apt-get install -f`

Download Google earth 

https://www.google.com/earth/download/gep/agree.html


------

## WebDev Apps

>**ATOM** - A hackable text editor for the 21st Century

https://atom.io/

**Packages for Atom**

- open-terminal-here
- terminal-fusion
- minimap
- logo-file-icons
- color-picker

```
bambang@idbmb  ~/fonts/DejaVuSansMono   master ●  sudo mv DejaVu\ Sans\ Mono\ for\ Powerline.ttf /home/bambang/.fonts/
```

>**ZSH** - Zsh is a shell designed for interactive use, although it is also a powerful scripting language. More information can be found on the "Zsh Web Pages" sites.

`apt install zsh`

`sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"`

References : https://github.com/robbyrussell/oh-my-zsh

Change your default shell

`chsh -s /bin/zsh`

manual update

`upgrade_oh_my_zsh`

Magic!

Themes Agnoster

References : https://github.com/robbyrussell/oh-my-zsh/wiki/Themes#agnoster

**Powerline installation**

`sudo apt-get install python-pip`

`pip -V`

References : https://powerline.readthedocs.io/en/latest/installation/linux.html#font-installation

`pip install powerline-status`

`pip install --user git+git://github.com/powerline/powerline`

`pip install --user --editable={path_to_powerline}`

`ln -s {path_to_powerline}/scripts/powerline ~/.local/bin`

**Fonts installation**

`wget https://github.com/powerline/powerline/raw/develop/font/PowerlineSymbols.otf`

`wget https://github.com/powerline/powerline/raw/develop/font/10-powerline-symbols.conf`

`sudo mkdir ~/.fonts/`

`mv PowerlineSymbols.otf ~/.fonts/`

`fc-cache -vf ~/.fonts/`

`sudo mkdir ~/.config/fontconfig/conf.d/`
if error create directory manual.

`mv 10-powerline-symbols.conf ~/.config/fontconfig/conf.d/`

References : https://github.com/powerline/fonts

`git clone https://github.com/powerline/fonts.git`

`cd fonts`

Run `./install.sh`

References : https://github.com/agnoster/agnoster-zsh-theme

------

>**NVM** - Node Version Manager - Simple bash script to manage multiple active node.js versions

References : https://github.com/creationix/nvm

**Install NVM**

`wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash`

**Verify installation**

`command -v nvm`

**Manual Upgrade**

For manual upgrade with `git` (requires git v1.7+):

1. change to the `$NVM_DIR`
1. pull down the latest changes
1. check out the latest version
1. activate the new version

```sh
(
  cd "$NVM_DIR"
  git fetch origin
  git checkout `git describe --abbrev=0 --tags --match "v[0-9]*" origin`
) && . "$NVM_DIR/nvm.sh"
```

**Usage**

To download, compile, and install the latest release of node, do this:

```sh
nvm install node
```

And then in any new shell just use the installed version:

```sh
nvm use node
```

Or you can just run it:

```sh
nvm run node --version
```
Or, you can run any arbitrary command in a subshell with the desired version of node:

```sh
nvm exec 4.2 node --version
```

You can also get the path to the executable to where it was installed:

```sh
nvm which 5.0
```

In place of a version pointer like "0.10" or "5.0" or "4.2.1", you can use the following special default aliases with `nvm install`, `nvm use`, `nvm run`, `nvm exec`, `nvm which`, etc:

 - `node`: this installs the latest version of [`node`](https://nodejs.org/en/)
 - `iojs`: this installs the latest version of [`io.js`](https://iojs.org/en/)
 - `stable`: this alias is deprecated, and only truly applies to `node` `v0.12` and earlier. Currently, this is an alias for `node`.
 - `unstable`: this alias points to `node` `v0.11` - the last "unstable" node release, since post-1.0, all node versions are stable. (in semver, versions communicate breakage, not stability).

------

**SQLite**

`sudo apt-get install sqlite3`

`sudo apt-get install sqlitebrowser`

**PostgreSql**

`sudo apt-get install postgresql`

**pgAdmin III available on software center**

pgAdmin III is a database design and management application for use with PostgreSQL. The application can be used to manage PostgreSQL 7.3 and above running on any platform.

**FileZilla**

`sudo apt-get install filezilla`

**Android Studio**

https://developer.android.com/studio/index.html

Solved : Unable to run mksdcard SDK tool.

`sudo apt-get install lib32z1 lib32ncurses5 lib32stdc++6`

**Xampp**

https://www.apachefriends.org/download.html

`sudo chmod +x xampp-linux-x64-7.1.1-0-installer.run`

`sudo ./xampp-linux-x64-7.1.1-0-installer.run`

`cd /opt/lampp`

`sudo ./manager-linux-x64.run`

Create Shortcut

`sudo gedit /usr/share/applications/xampp-control-panel.desktop`

```
[Desktop Entry]
Encoding=UTF-8
Name=XAMPP Control Panel
Comment=Start and Stop XAMPP
Exec=gksudo /opt/lampp/manager-linux-x64.run
Icon=/opt/lampp/htdocs/favicon.ico
Categories=Application
Type=Application
Terminal=false
```

`sudo apt-get update`

-------

## Troubleshooting

**If Touchpad not work normal**

`sudo modprobe -r psmouse`

`sudo modprobe psmouse proto=imps`

**if after reboot not working**

Here is something that fixed touchpad issues for me on some Dell Latitude e6220 laptops with TeaLinuxOS 8.1 versions.

`sudo mkdir /etc/X11/xorg.conf.d`

`cd /usr/share/X11/xorg.conf.d`

`sudo cp 50-synaptics.conf /etc/X11/xorg.conf`

`sudo cp 50-synaptics.conf /etc/X11/xorg.conf.d`

`cd /etc/X11/xorg.conf.d`

`sudo pico 50-synaptics.conf`

under the line saying "MatchDevicePath "/dev/input/event*" in the first "InputClass" section, insert these two lines:

```
# Enable ClickPad to fix drag/drop on some laptop models
Option    "ClickPad"   "1"

```

Save and exit editor and than reboot

**Get to default TeaLinuxOS lock screen After change the lock screen**

`sudo nano -B /etc/lightdm/lightdm.conf`

```
[SeatDefaults]
greeter-session=lightdm-gtk-greeter
```

**Sometimes fails to sleep**

To fix, try installing a new kernel.

Open your terminal then just copy paste the command

```
cd /tmp

wget \
kernel.ubuntu.com/~kernel-ppa/mainline/v4.5.2-wily/linux-headers-4.5.2-040502_4.5.2-040502.201604200335_all.deb \
kernel.ubuntu.com/~kernel-ppa/mainline/v4.5.2-wily/linux-headers-4.5.2-040502-generic_4.5.2-040502.201604200335_amd64.deb \
kernel.ubuntu.com/~kernel-ppa/mainline/v4.5.2-wily/linux-image-4.5.2-040502-generic_4.5.2-040502.201604200335_amd64.deb

sudo dpkg -i linux-headers-4.5*.deb linux-image-4.5*.deb

```

## Permission

Directory permissions change "directory" and all of its contents.

`chmod 777 -R /directory`
