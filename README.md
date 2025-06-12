# **simple-ctwm-retro-blue**
A Minimal and Non-Invasive set of configurations to pair up a modern, usable and good RETRO looking CTWM setup

## **CTWM Retro Rice**
![rice3](https://github.com/user-attachments/assets/f117edd2-c5c5-4f46-91e1-785019020188)
![rice5](https://github.com/user-attachments/assets/1a30b994-fa1e-44c4-9b68-2e5548afc4d7)


## **Installation:**
### Required Packages:
```
1. ctwm
2. feh
3. picom
4. xrdb
5. xev
6. xterm
7. conky
8. thunar
9. pipewire
10. polkit-gnome
11. nmcli
12. dejavu-fonts-ttf
13. xorg-fonts
14. noto-fonts-ttf
15. noto-fonts-cjk
16. xfontsel
17. xlsfonts
18. pamixer
19. xdg-desktop-portal
20. xdg-desktop-portal-gtk
21. loginctl
22. alttab
```
Install these packages using your distro's package management tools and enable their service(s) if required.

---

## **GTK,Icon themes and Font:**
1. **Doormaker GTK:** https://www.xfce-look.org/p/2098041
2. **Elementary GTK icons:** https://store.kde.org/p/1102953
3. **Font:** Luxi Mono Family
4. **Wallpaper:** https://wall.alphacoders.com/big.php?i=1371840
---

## **Installing the RICE:**
1. Download this repository.

2. Unzip it in a desired folder.

3. Copy `dotctwmrc` into your home directory as `.ctwmrc`

   - To do so:
        - Open a terminal in the folder containing the unzipped repository.
        - Run:\
         `cp dotctwmrc ~/.ctwmrc` in the terminal.
        - This will override your custom `.ctwmrc` in your home directory

4. Copy `dotconfig` into your home directory as `.config`

    - To do so:
         - Open a terminal in the same folder as above.
         - Run:\
          `cp -r dotconfig/* ~/.config` in the terminal.
         - This will override your custom: `picom.conf` , conky configuration and xresources configuration(if configured).

5. Copy `CTWMscripts` folder in your home directory.

6. Copy `usr` folder in your `/usr` folder.
   - To do so:
        - Open terminal as in step 3.
        - run: `sudo cp -r usr/include /usr`.

8. Verify that the copied files/folder are copied correctly in the correct folder:
   
   |    Repository Folder    |                  Content                 |                       System Folder                                |
   | ----------------------- | ---------------------------------------- | ------------------------------------------------------------------ |
   |         `usr`           | is same as,and/or has similar content as |        `/usr`                                                      |
   |         `dotconfig`     | is same as,and/or has similar content as |        `~/.config` or `/home/USER_NAME_HERE/.config`               |
   |         `dotctwmrc`     | is same as,and/or has similar content as |        `~/.ctwmrc` or `/home/USER_NAME_HERE/.ctwmrc`               |
   |         `CTWMscripts`   | is same as,and/or has similar content as |        `~/CTWMscripts` or `/home/USER_NAME_HERE/CTWMscripts`       |


   
9. Done !

---
   
## **Features:**
1. Mouse cursor controls window focus
2. Icons arranged from Top Left to South and following similarly throughout the screen area.
3. Applications Task manager like Icon Manager at the bottom of the screen.
4. Conky Widget to display date and time.
5. Left click on windows below other windows raises them above.
6. Left click on wallpaper/root window opens up a menu with several entries/functions.
7. `Shift+Control+F` allows to take screenshot using cursor.
8. `Ctrl+F2` and `Ctrl+F3` allow to change the volume in increments/decrements of 10% of the total volume.
9. Sleep and suspend available from the left-click menu.
10. Configurable Alt-tab menu.
    
---

## **Tuning the RICE:**
#### .ctwmrc
1. Paths of folders and files need to be adjusted according to your setup.

2. Device specific commands like `nmcli`, and similar need to be adjusted for your device.\
   **Ex:** Use `nmcli device --help` and `nmcli device wifi --help`.

3. Icon Manager geometry maybe adjusted for other resolutions.\
   **See:** https://www.x.org/archive/X11R6.8.1/doc/X.7.html#toc6 and https://www.ctwm.org/manpage.html#_variables 

4. Icon Region maybe also adjusted for other resolutions.\
   **See:** https://www.x.org/archive/X11R6.8.1/doc/X.7.html#toc6 and https://www.ctwm.org/manpage.html#_variables 

   **Hint:** The icon region is a region on the screen of desired size placed in the top or bottom or corner depending on the offsets described in the link(s) above.
         This region is then further divided into regions of size `x by y` as described in the CTWM manpage above and the icons are placed inside these regions.

5. For details on `Icons` , see https://www.ctwm.org/manpage.html#_variables \
   **Hint:** Icons of some applications maybe off or too big/small, their transparent icons maybe obtained, resized and exported in `.xpm` format using suitable software like GIMP.

7. For knowing the keyboard/mouse button names to be used for bindings, use the `xev` utility:
     - Open `xev` through terminal and hover the mouse over its window. The keypresses pressed afterwards while the `xev` window has focus will be captured and their name be displayed in the terminal output.    

---
   
#### **Picom**
For tuning the picom compositor: \
**See:** https://github.com/yshui/picom/blob/next/man/picom.1.adoc \
A sample configuration maybe obtained from: `/usr/share/examples/picom` .

---

#### **CTWMscripts**
Replace `intel_backlight` in lines:

```
intel_backlight=$(cat /sys/class/backlight/intel_backlight/brightness)
neuebacklight=$(( $intel_backlight - 10000 ))
echo $neuebacklight|sudo tee /sys/class/backlight/intel_backlight/brightness      
```
   
In both the scripts: `backlightup` and `backlightdown` with your folder name respectively.\
**See:** https://wiki.archlinux.org/title/Backlight , section 1. Hardware Interfaces:1.1 ACPI

---

#### **Fonts**
Font size maybe be adjusted for other resolutions.\
**See:** https://wiki.archlinux.org/title/X_Logical_Font_Description and `xfontsel` utility.

---
   
#### **Alt-Tab**
**See:** https://github.com/sagb/alttab \
**And:** https://github.com/sagb/alttab/blob/master/doc/alttab.1.ronn


---

#### **Other**
All the entries in the menu that appears upon left-clicking on the wallpaper/root-window are pretty much self explanatory.

---

### **End**

---

## **See also:**

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
10. https://wiki.archlinux.org/title/Polkit
11. https://linux.die.net/man/1/xterm
12. https://github.com/sagb/alttab

---

## **Credits:**

1. Software developers of the utilized software.
2. https://github.com/junaidrahim/conky-clock?tab=readme-ov-file for Conky.conf
3. WallpaperAbyss for the wallpaper.

# Cheers!
