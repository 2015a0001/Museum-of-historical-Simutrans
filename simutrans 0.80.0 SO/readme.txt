Simutrans supports some commandline options, the current options include:


1.) Choose a resolution:

1a.) Choose a 'standard'  resolution

simuwin -res n

where n is one of 1,2,3,4,5

The switch -res chooses the resolution at program start:

1 = 640x480
2 = 800x600
3 = 1024x768
4 = 1280x1024

Resolution no. 5 runs Simutrans in a window instead of fullscreen mode 
(Windows version only)

Use this switch at your own risk! Using a wrong resolution may damage your
monitor! Up to date monitors should support all resolutions, but older
monitors may have problems with the higher resolution settings. Don't expect
all resolutions to be available with your graphics card. The program will
abort the starting process if the graphics card doesn't support the chosen
resolution.

The default resolution was 640x480. Simutrans version 0.78.4 and newer
have a default resolution of 800x600. Please note that bigger resolutions
slow down the game. If Simutrans runs too slowly on your system, use a
smaller screen resolution. Windowed mode (-res 5 on Windows) is always
slower than full screen resolutions.
                           

1b.) Choose a non-standard resolution

simuwin -screensize 900x400

More general the syntax is -screensize widthxheight
where width and height are integral values separated by a small x
This format is strict. Simutrans will not tolerate spaces or other
format elements.

If the number matches a resolution your graphic card can display in
fullscreen mode Simutrans will run in fullscreen mode. If not, Simutrans
will run in a windowed mode (Linux versions always runs windowed).

Use with care! I'm sure you can screw up things if you use values which
are not supported by your system. Use on your own risk ... i.e.
using -screensize 1600x1400 might damage your monitor if the graphics
card switches to that resolution, but your monitor cannot! I give
absolutely no warranty for any results of using that option!!!

Please note that if width is set below 640, parts of the toolbar will
not be visible and can't be used. In general setting width to less than 640
and height to less than 400 will most likely cause trouble ... the program 
does not check the values! As said above, use with care, no warranties are 
given!


2.) Copy output messages into a logfile:

simuwin -log

This writes all messages which are output after the game switches to graphics
mode to a file named "simu.log". This file might be helpful when reporting
problems, you might consider to log a replay of the problem and send the log
file together with a problem report to hansjoerg.malthaner@gmx.de. Please 
zip (compress) large log files before sending them. Don't forget your
explantion of the problem is much more important than the log file when
reporting problems.


3.) Run Simutrans in free playing mode (unlimited money):

simuwin -freeplay


4.) Screen refresh setting:

On slow machines even updating 640x480 pixels each frame may be
too much load for the CPU. To run Simutrans on slow machines, frame
skipping can be activated. Vehicles may move less smoothly this way,
but at least it is possible to run Simutrans at all.
Maybe this is helpful for running the big resolutions on standard
machines, too.

simutrans -refresh n

displays every nth frame only. n=2 should result in a speedup of 25%,
n=3 in a speedup of 33%
You can chose n in a range from 1 to 16, where n=1 has the same effect as
omitting this setting at all. n >= 4 may result in 'jumpy' vehicle movement.

Try this at your own to find a usable setting for your hardware. Usually
n=2 or n=3 work best on slow machines. n=16 may be a kind of slideshow mode.


5.) Shared memory usage:

The Linux/X-Windows version uses shred memory by default. In network
environments this may not work. Use -net to turn shared memory usage off.

simutrans -net                                                    

(Simutrans versions 0.78.0 and newer autodetect shared memory. They do not 
use this switch, but just ignore it).


6.) Async screen updates:

The Linux/X-Windows can be forced to update the screen asynchroneously.
This may or may not improve the frame rate on your machine. On my setup
it turned out to be useless, but on other setups, this option has proven
helpful

simutrans -async

turns async screen updates on.

(Simutrans versions 0.78.0 and newer no longer support this switch.)


7.) Getting help (well it just says read this readme file)

simutrans -h
simutrans -?
simutrans -help
simutrans --help

All print a quick help message, which basically says 
"Read the readme file"


8.) Use alternative graphics pack

If you have an alternative graphics pack for Simutrans, such as the
winter scenario, you can use this either by naming it "daten.pak" or
using the following command line argument:

simutrans -graphicpack winter.pak

Please note that the name of the graphics pack *must* be after the
-graphicpack command line argument.

9.) Read altnerative scenario

simutrans -scenario <directory>

This switch makes Simutrans read all config files, color maps and
the daten.pak file from the given directory


All the above mentioned options can be combined, i.e.

simuwin -res 2 -log -graphicpack winter.pak

runs Simutrans in test mode, writes output to "simu.log", switches to
a resolution of 800x600 pixels and uses the winter graphics pack. Not
all options are available on all platforms, i.e. -async and -net are
only supported on Linux/X-Windows.


If you run into problems, or if you have questions, you can contact me
by email at:

hansjoerg.malthaner@gmx.de

Suggestions on how to improve Simutrans are also always welcome.

If you're unsure how to report problems or change request, there are
two example forms packaged with simutrans. Use "problem_report.txt"
for problem reports and "change_request.txt" for change requests.



There are some Simutrans related web pages, you may want to visit them:

The official Simutrans home page:
http://www.simutrans.de

A mirror of the official site (sometimes not up to date):
http://simutrans.drive.to



This readme file was written by Hansjörg Malthaner, November 2000,
Last update 20-Jan-2002
EMail: hansjoerg.malthaner@gmx.de
