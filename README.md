# How to install Blender addons - complete guide

[French version here](https://github.com/Pullusb/How_to_install_Blender_addons/blob/master/blender_addon_install_FR.md)

#### First, dear user, know that there can be two types of addon files

Single file addon:  
Just a plain python file "*the_addon_name.py*"

![single file addon](/imgs/single_file_addon.png)

Multi-file addon:  
A folder "*the_addon_name*" --> containing always (and at least) an "*\_\_init\_\_.py*" file.  
The folder of a multifile addon is nearly always downloaded zipped.

![multi-file addon](/imgs/multi-file_addon.png)


## Now how to install ?

### The easy (user friendly) Way

Go to preferences, addons, click on "install..." an look for either the "*.py*" or the "*.zip*".

![basic install](/imgs/basic_install.png)

Then just click on activate.

![activate addon](/imgs/activate_addon.png)


If you dont want to bother more, this is the only method you need to know (except if the addon use modules, most of them don't). So you can stop here. But!
The rest will be usefull to manage your addon more efficiently and personnaly.


Still there ? good !

## Manual install

Once an addon is manually installed in sources folders. You'll have to click on the refresh button to see it.

Let's see where addons (and python modules) are stored and the differences of these locations.  
There are 3 places :

### - Released

Placed in installation folder.

Something like : `C:\Program Files\Blender Foundation\Blender\2.80\scripts\addons\`

![release](/imgs/release.png)

"Release" addons (those who are built-in when you download blender) are stored inside the script folder of the blender datas.  
These are local to this blender version only, you can put your downloaded addon here, but the next place is plecisely designed for them.

> note that the intermediate RC (release candidate) versions also come with a lot more of "contrib" addons for you to test. If integrated, these are stored inside "addons_contrib" just aside "addons" folder. The "contrib" are those who didn't make it to the release for various reason but are usually solid and powerfull stuff.


### - User-addons

Placed in user apps configs.

Somewhere like this:  
on windows: `C:/Users/username/AppData/Roaming/Blender Foundation/Blender/2.80/scripts/addons`  
on linux: `~/user/config/blender/2.80/scripts`

![user scripts and config](/imgs/user_scripts_and_config.png)

This is where your file actually goes when you use the automatic install!  
Here is what happens when you click on install addon:
- Copy the "*.py*" or "*.zip*" in the User-addons location (unzip it there if it's a zip),
- Refresh the addon list so it will show up
- Bring it forward in the list via the name in search so only this addon appears.

>note : If you never installed addons from the "install" button the folder probably wont be there. You have create "addons" (and eventually "modules") if there are not in 'scripts'.


Why addons install here and not in blender datas ?  
Because this way you when you install the next version of Blender, or use a portable version, they all look here wherever they are installed (if version is the same) !

Bonus : For the same reason, that's also where your preferences are stored, aside the "script" folder there is a "config" that contains userpref.blend, startup.blend, file-history, etc.


### - External

Placed in a folder of your choice (optional and not set by default).

This place is defined by you in the preferences and allow a third folder to be scanned for addons and modules.  
You add the path in Preferences > File Paths > Scripts

![external scripts](/imgs/external_scripts.png)

The folder that you target must have the same directory structure as the two other location.  
In the directory that you point (you do not have to name it 'scripts') create a subfolder "addons" (and the folder "modules" if you need it)

This folder is interesting because you can even set the path to a local server for exemple.
So all the computer on the same network can load the same addons and updating the file will update for all.

---

That's it, now you know where the addons files are stored, you can manage them your own way.  <span>&#128077;</span>

> Final note : In the addon [DevTools](https://github.com/Pullusb/devTools) you have buttons to open these locations from blender in the text-editor toolbar.
  
  
Have a nice blend


Samuel Bernou (aka PullUSB)

![logo SB](/imgs/logo_sb_80px.png)