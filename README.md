![Screenshot](screenshot.jpg)
This screenshot is showing the two interfaces to muddler. In the background is muddler running in a terminal window. The foreground window is firefox connected to the same muddler session via websockets. Both are interactive and show the same data at the same time.

# muddler

   A simple perl based mudding client which hopes to be a drop in replacement for TinyFugue at some point. muddler can be run from your terminal and/or host sessions for your browser via websockets.
   The key 

# Features
```
   o Console support - Mudding via your favorite terminal
   o Http/websocket support - Think mudding via your browser
   o UTF8 support
   o Connect to multiple worlds at the same time in a single window
   o More / pausing output as needed
   o Multiple Window Support(?) - The console interface does not support
       multiple windows but multiple browser "windows" can be opened and
       can view different worlds.
```
# muddler goals
```
   o drop in replacement for TinyFugue. Not everything will be supported but
     maybe enough.
   o Simplified setup. TinyFugue is great but theres a little bit of a
     learning curve.
   o Allow users to switch between machines. All interfaces should be able
     to be started/stopped/resumed as the user switches between machines. 
     This assumes one can use screen/tmux for the terminal session.
   o The websocket and eventual native GUI should be better then just another
     way to see a terminal. Things will start off this way but hopefully
     will stay that way for long.
```
# Ideas to Impliment:
These are things things i plan to add in the future. Most of them will be done after the text based interface is extremely stable and usable.
```
   o Native GUI          Axmud has a perl based Gtk3 gui. The idea will be
                         that the gui can be turned on/off as needed. The
                         terminal interface will be the only always running
                         interface (or maybe not?)
   o Scripting Language  Either impliment something tinyfugueish in nature,
                         something new, or maybe include code from teeny-
                         mush for a mush like language?
```
# Installation
```
   Download the muddler perl script
   Install required perl modules
      muddler will tell you what modules are missing and how to install
      them if on a linux/deb system.
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
      Tab                : Both      : Move forward one screen full of text
                                       if the world is paused by "more".
      Control-l          : Console   : Redraw the screen 
      Escape-L           : Web       : Redraw the screen
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
