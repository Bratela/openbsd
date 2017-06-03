#  Install XFCE to OpenBSD 6.0
Login with the root user

Add your regular user to the wheel group

`user mod -G wheel youruser`


Set PKG_PATH environment variable

`export PKG_PATH=ftp://ftp.openbsd.org/pub/OpenBSD/$(uname -r)/packages/$(uname -m)`


Install nano text editor

`pkg_add -Iv nano`

Open and edit the .profile file

`nano .profile`


Add to the file

`export PKG_PATH=ftp://ftp.openbsd.org/pub/OpenBSD/$(uname -r)/packages/$(uname -m)`

Save and exit
Ctrl+x


Install Xfce

`pkg_add -Iv xfce
`

Install Slim

`pkg_add -Iv slim slim-themes
`


Open and edit the root user `.xinitrc` file

`nano .xinitrc`

Add to the file

`exec startxfce4`


Save and exit

Ctrl+x


Change to the home directory of your regular user

`cd /home/youruser`


Open and edit your regular user `.xinitrc` file

`nano .xinitrc
`
Add to the file

`exec startxfce4`


Save and exit

Ctrl+x


Open and edit `rc.local`

`nano /etc/rc.local`


Add to the file

`/usr/local/bin/slim -d`


Save and exit

Ctrl+x


Open and edit rc.conf.local

`nano /etc/rc.conf.local`


Add to the file

`pkg_scripts="dbus_daemon avahi_daemon"`

`dbus_enable=YES`

Save and exit
Ctrl+x

Install some basic applications

`pkg_add -Iv firefox thunderbird gimp vlc libreoffice`

Reboot
