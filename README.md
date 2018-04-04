QLNetcdf
========
A QuickLook Plugin for previewing [NetCDF](http://www.unidata.ucar.edu/software/netcdf/) files. Use spacebar when navigating in macOS Finder to view the header (info output by `ncdump -h`) for NetCDF files.

This is a slight edit of https://github.com/tobeycarman/QLNetcdf that uses [MacPorts](https://www.macports.org) instead of [Homebrew](http://brew.sh).


Example
-------
Here is an example.

![Screen shot](/images/example0.png?raw=true "QLNetcdf generator in action")

Installing
-----------
__QLNetcdf requires that `ncdump` is installed at `/opt/local/bin/ncdump`__

Fortunately if you installed `netcdf` using [MacPorts](https://www.macports.org) (with the default settings) then `ncdump` should exist in the correct location already. 

Then all you need to do is `git clone https://github.com/aekiss/QLNetcdf.git`, open `QLNetcdf.dmg` and copy the prebuilt executable `QLNetcdf.qlgenerator` to your `~/Library/QuickLook/` directory (or `/Library/QuickLook/` to make the plugin available to all users).

You may have to force the QuickLook Server to reload so it picks up the new generator:

    $ qlmanage -r


Known Issues
------------
Sometimes the plugin fails to work (no preview is rendered). The best fix I have found is to force-relaunch Finder (`cmd+option+esc`).

If you're using [Homebrew](http://brew.sh) you'll need to edit the code and rebuild - see below. Or you could use https://github.com/tobeycarman/QLNetcdf.

Building
--------
The xcode project file is supplied with the project. The project has been built with xcode 4.6, 5.1 and 9.2. The prebuilt executable `QLNetcdf.qlgenerator` was built with xcode 9.2 on macOS Sierra 10.12.6.

If you're using [Homebrew](http://brew.sh) (with the default settings) then `ncdump` is installed at `/usr/local/bin` instead - this can be handled by a simple edit in `GeneratePreviewForURL.m`. 

Note: building with Xcode will not replace the prebuilt binary in `bin`. To find your newly-built executable, click the Project Navigator (folder icon at top left of Xcode window) so that tree of files and folders is visible, right-click the `QLNetcdf.qlgenerator` executable in the Products folder and choose "Show in Finder".


