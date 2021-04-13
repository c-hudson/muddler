![Screenshot](screenshot.jpg)
This screenshot is showing the two interfaces to muddler. In the background is muddler running in a terminal window. The foreground window is firefox connected to the same muddler session via websockets. Both are interactive and can show the same or different worlds.

# muddler

   A perl based mudding reminiscent of TinyFugue with a few twists. 

# Features
```
   o Console support - Mudding via your favorite terminal
   o Http/websocket support - Think mudding via your browser
   o UTF8 support 
   o 256 color support
   o Inital fansi support
   o Multiple worlds at the same time
   o More / pausing output as needed
   o spell checking
   o Multiple Window Support(?) - The console interface does not support
       multiple windows but multiple browser "windows" can be opened and
       can view different worlds.
```
# muddler goals
```
   o Go for Simplicity.
   o Allow users to switch between computers with ease. The main muddler
     process still needs to run a particular server but viewing can be
     switched from computer to computer.
   o Make a rich and full featured web interface
   o Support a "language" either tinyfugue like or maybe mush?
     (mush is just an easy answer since i've already written a mush in perl)
```
# Installation
```
   Download muddler:
      For the easy of installation, the muddler perl script is packaged
      together as an executable for linux and windows. Using these packages
      is only ment for ease of installation.

      Download executable
         download pl_muddler for linux or
         download pw_muddler for windows

      or

      Download perl script "muddler" perl script and install required perl 
         a. download muddler script
         b. Install required perl modules.
            muddler will tell you what modules are missing

   chmod u+x muddler
   ./muddler <options>

   Options:
      --noconsole     : disable the text based console and enable the
                        web/websocket server.
      --password      : specify the password for the websocket interface.
      --port          : specify the port for the web server. The websocket
                        server will be one port number higher.
```
# Quick Start
   
```
   Basic Commands:
      /add <world> [<user> <password] <address> <port>
         Define a world so that muddler can connect with it. If a user and
         password are supplied, the user will be logged into at startup
      /world <world>
         Connect to an already defined world or switch to that world if
         the world has already ben opened. This can be done with the up/down
         arrow keys or escape-w.
      /help [<command>]
         Lists all commands or provides help on an individual command.
      /quit
         Had enough, quit muddler.
      /utf8
         Enable utf8 encoding for the current world. [default]
      /fansi
         Enable fansi encoding for the current world.

   Web Commands:
      /web <status>
         Turn the web interace "on" or "off". Default is off.
      /password <password>
         Sets the password that must be entered when connecting vai the web.
      /port <port>
         This command sets the port that muddler will use when you connect
         to muddler via your browser. Just type in http://localhost:<port>
         to connect. The default port is port 9000.

         Note: If you plan to connect outside your network to muddler, the
               program uses <port> for web traffic and <port> + 1 for web-
               sockets. i.e. /port 9000 would use ports 9000 and 9001.

   Command Line:
      ./muddler <options>

          --noconsole     : disable the text based console and enable the
                            web/websocket server.
          --password      : specify the password for the websocket interface.
          --port          : specify the port for the web server. The websocket
                            server will be one port number higher.
   Saving stuff:
      muddler saves your data automatically. This is only pointed out because
      programs like TinyFugue require you to issue a command.

   Supported Keys:

      Keys                 INTERFACE   DESCRIPTION
      Arrow Right & Left : Both      : Move one character in the buffer
      Arrow Up and Down  : Both      : Cycle to the next connected world.
      Escape-w           : Both      : Move to next active world
      Control-w          : Both      : Delete previous word [console only]
      Control-p          : Both      : Move down in the keyboard history
      Control-n          : Both      : Move up in the keyboard history
      Control-u          : Both      : Erase the current input line
      Control-q          : Console   : Spell check line and give suggestions
      Control-a          : Console   : Move to begining of input
      Control-e          : Console   : Move to end of input
      Tab                : Both      : Move forward one screen full of text
                                       if the world is paused by "more".
      Control-l          : Both      : Redraw the screen 
      PgUp               : Both      : Scroll up one page in history buffer
      PgDown             : Both      : Scroll down one page in history buffer
      Scroll Wheel       : Web       : Scroll up / Down in history buffer
```
# TinyFugue info/differences
```
   If you wish to use your TinyFugue world file, just rename it to ~/.tfworlds.
   This file will be read on startup as long as there is not a .muddler file
   to read. The TinyFugue world file will not be modified by muddler.

   Saving stuff? TinyFugue requires you to do a /saveworld as needed.
   Muddler automatically saves data as needed to its .muddler file.
