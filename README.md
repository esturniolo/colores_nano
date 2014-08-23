colores_nano
============

Agrega colores a la edicion de archivos de configuracion en nano



****************************************************
Fuente: https://bbs.archlinux.org/viewtopic.php?id=133595


*To install, save the above above code snippet as a file called conf.nanorc in the folder /usr/share/nano/ (or /usr/local/share/nano/ or similar if you feel strongly about the /usr <--> /usr/local separation), and then add the following to the end of the file /etc/nanorc:*

 
    ## Configuration files (catch-all syntax)
    include "/usr/share/nano/conf.nanorc"



*Hints:*
*The colors I chose look good (imo) with the terminal background and color settings that I use, but might not look good, or even readable, with yours, so simply change the color names in the code snippet to whatever you prefer - valid color names are: consolecolors.png*

*If you use a console with white background, you'll have to change at least the white color I chose for comments and punctuation.*
*The first code line in the snippet includes a regular expression that defines for which file names this syntax highlighting should be used. Whenever you encounter a config file that is not matched by this, but you would still like to open it with syntax highlighting, you can manually select this syntax with nano's -Y switch, like so:*


    nano -Y conf myConfigFile


*Technical Note:*
*It's implemented as a single catch-all syntax, since nano chooses which syntax to apply based on the filename, and in the case of config files usually not much can be learned about the content format from the file name extension (.conf can by anything from flat key/value tuples to XML, .ini can be the official INI format or something else, etc...).*
*This means that some compromises have been made, so with this highlighting syntax probably no config file looks 100% as good as a highlighting syntax that would be specifically optimized for one kind of config format, but all in all the vast majority of config files should look pretty good.*
