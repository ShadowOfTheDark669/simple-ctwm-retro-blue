# simple-ctwm-retro-blue
A Minimal and Non-Invasive set of configurations to pair up a usable and good RETRO looking CTWM setup

## CTWM Retro Rice
![rice3](https://github.com/user-attachments/assets/dbe545d2-15f0-4477-9e4b-0ee2dbef204c)

## Installation:
### Required Packages:
1. ctwm
2. feh
3. picom
4. xrdb
5. xfontsel
6. xev
7. xterm
8. conky
9. thunar
10. pipewire
11. polkit-gnome
12. pipewire
13. nmcli
14. dejavu-fonts-ttf
15. xorg-fonts
16. noto-fonts-ttf
17. noto-fonts-cjk


Install these packages using your distro's package management tools and enable their service(s) if required.

### GTK,Icon themes and Font:
1. Doormaker GTK: https://www.xfce-look.org/p/2098041
2. Elementary GTK icons: https://store.kde.org/p/1102953
3. Font: Luxi Mono Family

### Installing the RICE:
1. Download this repository.
2. Unzip it in a desired folder.
3. Copy `dotctwmrc` into your home directory as `.ctwmrc` . To do so, open a terminal in the folder containing the unzipped repository and run: `cp dotctwmrc ~/.ctwmrc` . This will override your custom `.ctwmrc` in your home directory,
4. Copy dotconfig into your home directory as `config` . To do so, open a terminal in the same folder as above and run: `cp -r dotconfig/* ~/.config` which will override your custom: `picom.conf` , conky configuration and xresources configuration(if configured).
5. Copy `CTWMscripts` folder in your home directory.
6. Copy `usr` folder in your `/usr` folder, open terminal as in step 3. and run: `sudo cp -r usr/include /usr`.
7. Verify that the copied files/folder are copied correctly in the correct folder:
   
   a. `usr/include` folder in repository should be same as `/usr/include` folder and have same/similar content(s) inside.

   b. `dotctwmrc` in repository should be same as `~/.ctwmrc` or `.ctwmrc` in the home folder.

   c. `dotconfig` folder in repository should be same as `~/.config` or `.config` folder in home directory and have same/similar contents inside. Same applies to the `CTWMscripts` folder.
   

   
9. Done !
   
### Features:
1. Mouse cursor controls window focus
2. Icons arranged from Top Left to South and following similarly throughout the screen area.
3. Applications Task manager like Icon Manager at the bottom of the screen.
4. Conky Widget to display date and time.
5. Left click on windows below other windows raises them above.
6. Left click on wallpaper/root window opens up a menu with several entries/functions.
7. Right click on `close` button makes the window maximized. Right click again restores it to former size.


### Tuning the RICE:
#### .ctwmrc
1. Paths of folders and files need to be adjusted according to your setup.
2. Device specific commands like `nmcli` and similar need to be adjusted for your device. Ex: Use `nmcli device --help` and `nmcli device wifi --help` .
3. Icon Manager geometry maybe adjusted for other resolutions, see: https://www.x.org/archive/X11R6.8.1/doc/X.7.html#toc6 and https://www.ctwm.org/manpage.html#_variables .
4. Icon Region maybe also adjusted for other resolutions, see: https://www.x.org/archive/X11R6.8.1/doc/X.7.html#toc6 and https://www.ctwm.org/manpage.html#_variables .

   Hint: The icon region is a region on the screen of desired size placed in the top or bottom or corner depending on the offsets described in the link(s) above.
         This region is then further divided into regions of size `x by y` as described in the CTWM manpage above and the icons placed inside these regions.

6. For details on `Icons` , see https://www.ctwm.org/manpage.html#_variables.

   Hint: Icons of some applications maybe off or too big/small, their transparent icons maybe obtained and resized using suitable software like GIMP.

7. For knowing the keyboard/mouse button names to be used for bindings, use the `xev` utility. Open `xev` through terminal and hover the mouse over its window.
   The keypresses pressed afterwards while the `xev` window has focus will be captured and their name be displayed in the terminal output.    
   
#### Picom
8. For tuning the picom compositor, see: https://github.com/yshui/picom/blob/next/man/picom.1.adoc. A sample configuration maybe obtained from: `/usr/share/examples/picom` .

#### CTWMscripts
9. CTWMscripts:
   Backlight:
   Replace `intel_backlight` in lines:
   1. `intel_backlight=$(cat /sys/class/backlight/intel_backlight/brightness)`
   2. `echo $neuebacklight > /sys/class/backlight/intel_backlight/brightness`   
   
   In both the scripts: `backlightup` and `backlightdown` with your folder name respectively. See: https://wiki.archlinux.org/title/Backlight , section 1.Hardware Interfaces:1.1 ACPI

#### Fonts
10. Font size maybe be adjusted for other resolutions. See: https://wiki.archlinux.org/title/X_Logical_Font_Description and `xfontsel` utility.
   
#### Other
11. All the entries in the menu that appears upon left-clicking on the wallpaper/root-window are pretty much self explanatory.

#### End

### See also:

Be sure to visit the following links:
1. https://www.ctwm.org/manpage.html
2. https://github.com/yshui/picom/blob/next/man/picom.1.adoc
3. https://www.x.org/archive/X11R6.8.1/doc/X.7.html#toc6
4. https://wiki.archlinux.org/title/Backlight
5. https://wiki.archlinux.org/title/Xterm#
6. https://wiki.archlinux.org/title/Display_Power_Management_Signaling#
7. https://wiki.archlinux.org/title/X_Logical_Font_Description
8. https://wiki.archlinux.org/title/Fonts
9. https://wiki.archlinux.org/title/Font_configuration

### Credits:

1. Software developers of the utilized software.
2. https://github.com/junaidrahim/conky-clock?tab=readme-ov-file for Conky.conf
3. WallpaperAbyss

### Cheers!
