Just a fork of this [excellent extension](https://github.com/lestcape/Gnome-Global-AppMenu) that I am using as part of [gnome-layout-manager](https://github.com/bill-mavromatis/gnome-layout-manager). I know that @lestcape is focusing on the functionality of the extension but I just wanted to fix some visual glitches.

Only 2 small changes made:
1) Fixed some padding issues in stylesheet.css  
2) Fixed conflict with Pixel Saver (wrong priority) using this [PR](https://github.com/lestcape/Gnome-Global-AppMenu/commit/af3bb76d8f43463540b14fea90aeb8246a41b0b0)

--------------------------------------------------------------------------

Gnome Shell Extension: Gnome Global Application Menu Version: v0.7-Beta
--------------
I don't want donations, I work only for users and not for companies or communities that receive money or donations.


This is a fork of an old extension I made for Cinnamon. The initial extension doesn't support Cinnamon anymore, as all extensions were `forked by Clement`

Latest update: 16 April 2017

***
Special thanks to:
--------------

- rgcjonas             (https://github.com/rgcjonas)               The initial code.
- Canonical devs       (http://www.canonical.com/)                 The protocols and patches.
- Cinnamon devs        (https://github.com/mtwebster)              Who help me to find the xsettings.
- Gnome Shell devs     (https://github.com/GNOME/gnome-shell)      The support.
- rilian-la-te         (https://github.com/rilian-la-te)           Understand and fix a lot of things.
- collinss             (https://github.com/collinss)               Has helped fix the behavior of firefox and thunderbird.

Author of language translation:
--------------
- Croatian(Hr):     gogo (trebelnik2@gmail.com)
- English(En):      Lester Carballo Pérez(lestcape@gmail.com)
- Spanish(Es):      Lester Carballo Pérez(lestcape@gmail.com)

--------------
![](https://raw.githubusercontent.com/lestcape/Gnome-Global-AppMenu/master/gnomeGlobalAppMenu%40lestcape/Capture.png)

Description
--------------
**Warning:** This is a third-party extension, not official.

This extension integrates the Ubuntu-Unity Application Menu (Global Menu) support into the Gnome Shell Desktop.

It's used the same idea of the Gnome Shell extension made by rgcjonas:

https://github.com/rgcjonas/gnome-shell-extension-appindicator

Known issues (Try at your own risk):
--------------
* Not all apps are tested, so the extension may take ages to load and freeze Gnome Shell forever.
* There are some unsupported apps that can't be integrated into the extension, like Blender, which has its own GUI toolkit.
* For some untested applications, it is possible a failure caused by a bug in the extension. Please, report it if is working in Unity.
* Some Gnome applications like Nautilus, remove the possibility to export the menu in recent versions (you can use alternative applications instead).

Experimental JAyatana support (Try at your own risk):
--------------
JAyatana is buggy and was removed intentionally from IntelliJ IDEA, Ubuntu 15.04 and others.

Currently you can use the JAyatana support as an option inside the extension. This will work for some java applications only and for others with several problems or even will not work at all. Sometimes you'll have to restart the Shell to see the menu, like for example with JDownloader.

I really don't know if this is caused by an improper handling of the JavaEmbeddedFrame by Mutter (The Gnome Shell Windows Manager), if it's a specific behavior/bugs of JAyatana or whatever. What occurs is that sometimes the JavaEmbeddedFrame can steal the menu to the main windows and some time not. So, a Shell restart after opening JDownloader would fix the problem in most cases, it's also possible that you'll need to kill the JDownloader process and open the application again in the others. To remove the experimental tag, the JAyatana project will need to implement this stuff at less:

1. Use the same sender in the DbusMenu implementation for the same windows and not a new one.
2. Use the same menu item id for all layout-updates and not a new one.

This is because force reload of all items is pretty hard for javascript.

Aditionally, we need to find out how to resolve the JavaEmbeddedFrame situation.

Changelog
--------------
0.7-Beta
 - Initialized the support into the Gnome Shell enviroment.

0.6-Beta
 - Added Croatian language, thanks to https://github.com/muzena
 - Added JAyatana support.
 - Added keyboard navigation.
 - Added effects.
 - Added vector box: https://github.com/linuxmint/Cinnamon/issues/1775.
 - Improved the menu speed (preload kde menu when is possible).
 - Fixed some issues.

0.5-Beta
 - Fixed Firefox, Thunderbird and Mint Update Manager.
 - Some little performance improvement.
 - Removed the utility file.

0.4-Beta
 - Now the gtk submenu will be updated when opening (will fix some other problems for Open Office).
 - Fixed the extension domain translation.
 - Corrections in the submenus operations.
 - Fixed other internal problems.

0.3-Beta
 - Don't show icon on the panel submenu item, is ugly and out of the standard.
 - Use a Shell radiobutton instead of an special text.
 - Try to add more gtk icons using the action context (could be wrong).
 - Add an option to desaturate the internal items icon.
 - Fixed the extension instance id problem in settings.
 - Try to fix Open Office (Is possible that will not show the menu on some contexts).

0.2-Beta
  - Not crash the Shell when firefox drop the menu.
  - Fixed xchat and possible other gtk applications.

0.1-Beta
  - Initial release.

This program is free software:
--------------
You can redistribute it and/or modify it under the terms of the GNU General Public License as published by the
Free Software Foundation, either version 2 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied
warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program.
If not, see http://www.gnu.org/licenses/.

Guidelines for bug reports
--------------
Unfortunately, this extension is not completely bug free and will probably never be.
In order to successfully resolve the issues you need to provide some data:

* Your distribution, Shell version and extension version (something like "latest git" or "latest from spices" is sufficient).
* Instructions how to reproduce it. **This is the single most important point**. Bugs that [can't be reproduced](http://xkcd.com/583/) can't be fixed either.
* Bugs which don't provide the necessary information may be closed as "invalid" without prior notice.

To report bugs, request new features and make suggestions, please visit:

https://github.com/lestcape/Gnome-Global-AppMenu/issues

You can also send us a pull request:

https://github.com/lestcape/Gnome-Global-AppMenu/pulls

Installation instructions:
--------------
1. Install the unity-gtk-module packages (explanation below).
2. Restart your computer.
3. Download this extension from its website: https://github.com/lestcape/Gnome-Global-AppMenu
4. Unzip the downloaded file and copy the folder gnomeGlobalAppMenu@lestcape to ~/.local/share/gnome-shell/extensions/
5. Enable the extension in Gnome Tweak Tool.
6. Log out and then back in.

unity-gtk-module:
--------------
This extension is designed to be used with the standard gtk modules packages (https://launchpad.net/unity-gtk-module) and patches that Ubuntu provide to
be used on Unity desktop.

You will probably need to use some equivalent packages depending on your specific distro.

* Ubuntu users, be happy, you don't need to do anything if unity is working. :)
* Mint users, all Ubuntu packages that we needed are availables on Mint repositories as well and can be installed.
  - Minimum requirements: sudo apt-get install unity-gtk2-module unity-gtk3-module
* Arch users, you will need to use the rilian-la-te source (https://aur.archlinux.org/packages/?SeB=m&K=rilian).
* Fedora users, the unity-gtk-modules are in the official repositories.

This extension can only read the standard Dbus menu structure (Gtk/Kde), so we can't resolve or patch directly any problematic application that not export the menu, or if is not exported properly. We also can't do anything if you used an alternative internally implementation that not export the DBus menu structure for some applications.

We are happy to include the support to any alternative implementation, if is provided an appropriate Dbus menu structure.

Uninstall instructions:
--------------
1. Disable the extension.
2. Reset the gsettings values:

  * ```gsettings reset org.gnome.settings-daemon.plugins.xsettings overrides```
  * ```gsettings reset org.gnome.settings-daemon.plugins.xsettings enabled-gtk-modules```

3. If you don't use a global menu in other desktop, remove also the packages that you install.
Restart your computer.

==============
Thank you very much for using this product.
Lester.
