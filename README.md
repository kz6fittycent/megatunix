# megatunix
This is an attempt to create a snap for "Megatunix"

-----------------------------------------------------------------------------------------------------------------------

MegaTunix

Designed and written by David J. Andruczyk

Overview

MegaTunix is a tuning application for Linux, Mac OS-X, other Unix variants and Windows XP/Vista/7 32 bit variants. It supports some of the available DIY EFI Fuel injection solutions including many MegaSquirt products and LibreEMS. It's written in C using the GTK windowing toolkit and is licensed under GPL V2.

More Detail

Most MegaSquirt 1/2 (MS1, MS1-Extra, MS2, MS2-Extra) firmwares are supported. MegaTunix has been redesigned in such a way as to be extensible via plugins to support new firmware variants with much greater ease than previously. The Gui design permits the gui tabs that relate to ECU variables to be redesigned using the Glade gui designer for Unix like OS's to change or alter the gui look/feel to accomodate new controls on more advanced firmwares.

MegaTunix is a native application, i.e. It is not written in a language like Java or Python that needs to be interpreted resulting in higher than wanted resource consumption. Thus it is a bit freindlier on the CPU than the competitors (best performance in a modern Linux or OS-X system).

MegaTunix is developed on Linux (Ubuntu specifically), but does work on all other Linux distros (Assuming the proper libraries are installed), FreeBSD and Mac OS-X (with macports+ the necessary support libraries installed) and Win32 platforms as well.

Getting It

MegaTunix is best built from source due to constantly changing firmware versions. If you're using Linux or Mac OS-X it is straight forward to do that, however if you're on Windows you need to request an up to date version from someone with a working cross-compiler mingw build environment. The previous release is now very old and lacking a lot of enhancements and refinements present in current source versions of the application.

Support

If you've made an honest attempt to resolve your issues by searching and trying things out, it's time to ask someone in-the-know for help. You can make contact one one of two forums, via email, or over IRC.

MSExtra forum: http://www.msextra.com/forums/viewforum.php?f=106
LibreEMS forum: https://forums.libreems.org
FreeNode IRC: ##megasquirt, #libreems-dev, #libreems
Dave's Email: dandruczyk gmail com
Using a public medium reduces the load on Dave by allowing others the opportuniy to help by answering questions and offering advice.

History

Inspiration for this code came from Bruce Bowling and Al Grippo, designers of the MegaSquirt DIY Fuel Injection ECU. This code was initially modelled slightly after Bruce and Al's MegaSquirt PCC tuning software for Windows. Inspiration also came from Eric Fahlgrens and Guy Hill's MegaTune, also for Windows. Since that time it has turning into it's own original application with many benefits and differences from MegaTune and other tuning softwares.

About Fonts

Some people have complained that MegaTunix comes up with abnormally huge fonts. This is NOT MegaTunix's fault. It's caused by the default font for Gnome being set to large. This problem is mostly seen by people NOT using the Gnome desktop. MegaTunix uses the GTK+2 libraries which are the foundation libraries by which Gnome's gui is based upon. The fix is to run "gnome-font-properties" and set the "Application Font" size to a smaller point size. On the authors' system a Application Font of "Sans" at 8pt, looks the best. The author runs at 1920x1200 on an 23" flatscreen monitor so your ideal font size may vary.

Suggestions

Suggestions are welcomed for improving the functionality of MegaTunix... Send suggestions, bug reports and general feedback to (SPAM not welcome) dandruczyk gmail com

System Requirements

MegaTunix is developed on Ubuntu Linux (10.04), the package names may vary if you don't use Ubuntu. Most RPM and Debian based distros split packages into a runtime and devel package. Runtime ones are needed to run the program, and devel packages are needed for programs like MegaTunix to be compiled.

MegaTunix requires the following libraries (and their dependencies):

minimum gtk+-2.18 GTK+ depends on pango, fontconfig, freetype2, glib and atk
Gtkglext-1.x gtkglext depends on opengl, gtk+ and glib
Libglade-2.x libglade depends on libxml-2.x and gtk+2.x
Optional

The optional Glade GUI designer can be installed to modify and add new gui tabs to MegaTunix for your own custom firmware needs. This is ONLY needed if you want to modify MegaTunix or design custom tabs for your firmware.
I recommend glade-2.x as 3.x has several performance and UI issues.
Unfortunately glade-2.x doesn't appear to be available with the current Linux distros (Ubuntu Releases after late 2010 does not have glade-2.x)

Version Control

As of 4/26/2010 MegaTunix has moved version control into Git from CVS, which is no longer supported or updated.

To obtain a copy using git move to your preferred directory and run:

git clone git://github.com/djandruczyk/MegaTunix.git
To keep that copy up to date run:

git pull
From within the MegaTunix directory.

Build Advice

To generate the necessary files after obtaining new source (either by download, git clone or a git pull update) run "./autogen.sh" in the top level directory.

It's REQUIRED to run "./autogen.sh" after every git pull in case I, the developer changed the configure.ac or Makefile.am files.
autogen will take care of creating the files that depend on those so that you don't end up with build problems...

As for the automake/autoconf warnings, in 99.995% of the cases it's safe to ignore those warnings. You can thank the autofoo tool maintainers for those warnings. Trying to make them go away tends to break other platforms.

After installing via "make install" you need to run "sudo ldconfig" so the system linker can pickup the new shared libraries that megatunix installed
