# installSWGonLinux
How to install Star Wars Galaxies for SWGEmu on Ubuntu based linux. 
Refer back to my previous post for the first two steps to this process of getting the files from your discs. (https://www.swgemu.com/forums/showthread.php?t=226002).

Once you have the files from your discs move them to a folder of your choice. You should not need to make ISOs out of them. If you do then follow my instructions in my last post to create the ISO files.
1) Install wine to your system.
> apt install wine

2) Run wine config without sudo.
> winecfg

3) Verify .wine was created in your home directory.
> cd /home/username>/.wine

4) Navigate into your drive_c file and create a folder called "Binaries" and within that directory create another directory called "StarWarsGalaxiesEmpireDivided" (If you used this game disc title)
> cd /home/<username>/.wine/drive_c
> mkdir Binaries
> cd Binaries
> mkdir StarWarsGalaxiesEmpireDivided

5) Move your disc files you copied over to your hard drive earlier into this directory. Do this through the GUI or through your terminal.
Ex. > mv dir/to/folder/<SWGEDFiles> /home/<username>/.wine/drive_c/Binaries/StarWarsGalaxiesEmpireDivided

6) Before installing we need the qtlibraries. QT5-default is defunct so you will need to download a few other libraries that should do the same thing as the qt5-default package.
> sudo apt install qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools libqt5webkit5
(Once done installing move to next step)

7) Navigate into your Disc1 folder within your newly created directory and list out the contents of the directory.
> cd StarWarsGalaxiesEmpireDivided/Disc1
> ls

8) Look for Setup.exe and run with wine.
> wine setup.exe
(Let this install to its default directory)

9) When asked for the first disc navigate the drop down to the directory you have placed your disc 1 folder. It should only ask for this disc as it will pull from the other discs automatically in
the same directory.

10) Once completed, download the launchpad files for ubuntu and drag/drop the three files into the following directory:
> /home/<username>/.wine/drive_c/Program Files (x86)/StarWarsGalaxies

11) Right click on the SWGEmuLaunchpad and go to Permissions and check the box "Allow executing as a program" and close the window.

12) Double-click the Launchpad and you should see the launchpad screen.

13) Go to Settings > Install from SWG.
(Note* : You may not see ./wine directory so right click in the blank space and choose “show hidden folders” then navigate through ./wine .
Filepath : ” ./wine/drive_c/’Program Files(x86)’/StarWarsGalaxies “ for both SWG and SWGEmuLaunchpad when asked)

14) From here it will update the game files and you should be good to go once it is finished.

--------------------------

If you want a .desktop file to add to your dock to launch the application rather than navigating the wine folder every time you want to play do the following:

1) Find a picture you want to use as an icon and save it to a folder you know you can find. I took the one from the SWGEmu reddit page


2) In the terminal navigate to:
> cd /usr/share/applications

3) Open your text editor (vim, vi, gedit) and enter the following:

> [Desktop Entry]
> Name=SWGEmu
> Type=Application
> Exec=/home/<username>/.wine/drive_c/Program\ Files\ (x86)/StarWarsGalaxies/SWGEmuLaunchpad
> Terminal=false
> Icon=/Directory/to/Image (/home/<username>/Pictures/swgemuicon.png
> Categories=Game

4) Save the file as SWGEemu.desktop

5) Go to your applications and you should see a new icon with the name SWGEmu in your apps. Right click and add to your dock.

Hope this helps out some people.
