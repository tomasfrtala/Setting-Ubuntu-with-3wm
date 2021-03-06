# Setting Ubuntu 18.04 with i3wm

After fresh install of Ubuntu 18.04 with Unity do this steps

## Adding the latest version of i3 from official sources
As super user run this command:
```
sudo echo "deb http://debian.sur5r.net/i3/ $(lsb_release -c -s) universe" >> /etc/apt/sources.list.d/i3.list
```
After that run:
```
sudo apt-get update
sudo apt-get --allow-unauthenticated install sur5r-keyring
sudo apt-get update
```
After that install i3 via command:
```
sudo apt-get install i3 \
xbacklight \
feh \
volumeicon-alsa \
fonts-font-awesome
```

## Tweaks
For getting hotkeys for controlling sound working you can open setting for volumeicon by right clicking on the icon and choose Preferences->Hotkeys and check them. Alternatively you can define yourself hotkeys in the ~/.i3/config file.

For simplification of work with file-manager create the startup script in
```
sudo gedit /usr/local/bin/n2autilus
```
And insert lines
```
#/bin/bash
nautilus --no-desktop
```
Lastly make it executable:
```
sudo chmod 755 /usr/local/bin/n2autilus
```
~~If you want to have unity-control-center to display all entries then based on this thread~~
~~http://askubuntu.com/questions/766775/ubuntu-doesnt-give-the-correct-keycodes-for-some-media-keys~~
~~then add at the end of your profile file~~
```
vim .profile
```
~~this line:~~
```
export XDG_CURRENT_DESKTOP=Unity
```
## Post install
If you are interested in automation of these processes, read the ubuntu-post-install.sh remove any unwanted commands, make it executable and run ;)

---

Credits for wallpaper belongs to Mustafa Kareem
https://www.flickr.com/photos/126031328@N05/15683734850
