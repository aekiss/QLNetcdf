QLNetcdf
========
A QuickLook Plugin for previewing 
[NetCDF](http://www.unidata.ucar.edu/software/netcdf/) files. Use 'spacebar' 
when navigating in OSX Finder to view the "header" (info ouput by `ncdump -h`) 
for NetCDF files.

__Requires that `ncdump` is installed at `/opt/local/bin/ncdump` !__

Fortunately if you installed `netcdf` using [MacPorts](https://www.macports.org) (with 
the default settings) then `ncdump` should exist in the correct location 
already.

If you're using [Homebrew](http://brew.sh) (with 
the default settings) then `ncdump` is installed at `/usr/local/bin` instead - this can be handled by a simple edit in `GeneratePreviewForURL.m`.


Example
-------
Here is an example.

![Screen shot](/images/example0.png?raw=true "QLNetcdf generator in action")

Installing
-----------
Download one of the releases and copy the QLNetcdf.qlgenerator file to your 
`~/Library/QuickLook/` directory (or `/Library/QuickLook/` to make the plugin 
available to all users).

You may have to force the QuickLook Server to reload so it picks up the new 
generator:

    $ qlmnange -r

Known Issues
------------
Sometimes the plugin fails to work (no preview is rendered). The best fix I
have found is to force-relaunch Finder (`cmd+option+esc`)

Building
--------
The xcode project file is supplied with the project. The project has been built
with xcode 4.6 and xcode 5.1
