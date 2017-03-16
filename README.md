# MyTLOS
Repository for help me installing some important tools on my laptop, based on TeaLinuxOS 8.1 Peppermint 64-bit Build on Ubuntu 16.04 - http://tealinuxos.org/

### Desktop Setting
**[optional theme]**

`sudo sh -c "echo 'deb http://download.opensuse.org/repositories/home:/Horst3180/xUbuntu_16.04/ /' > /etc/apt/sources.list.d/arc-theme.list"`

`sudo apt-get update`

`sudo apt-get install arc-theme`

`setting --> appearance --> Arc-Darker`

**[used themes]**
[macOS-Sierra](https://github.com/B00merang-Project/macOS-Sierra)

**[used icons]**
[la-capitaine-icon-theme](https://github.com/keeferrourke/la-capitaine-icon-theme)

`cp -r` copy directory along the entire file contents

change the background (oke.png its my background filename) :
`sudo cp /home/bambang/Pictures/Wallpapers/oke.png /usr/share/xfce4/backdrops/`

**Dock**

*Installing cairo-dock available at **software center**.*

remove the line above dock (cairo-dock)

`settings --> window manager tweaks --> compositor`

**uncheck :** *Show shadows under dock windows*

------

### Application

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
at use application# **enter 1 *Its a Files  (nautilus-folder-handler)**


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
