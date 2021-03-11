![Screenshot](screenshot.jpg)
This screenshot is showing the two interfaces to muddler. In the background is muddler running in a terminal window. The foreground window is firefox connected to the same muddler session via websockets. Both are interactive and show the same data at the same time.

# muddler

   A simple perl based mudding client which hopes to be a drop in replacement for TinyFugue at some point. muddler can be run from your terminal and/or host sessions for your browser via websockets.
   The key 

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
   ./muddler
```

# World Support
   Worlds may be defined in your ~/.tfworlds directory. Currently the
format of the file is exactly the same as tinyfugue's.
# Supported Keys:
```
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
   PgUp               : Both      : Scroll up one page in the history buffer
   PgDown             : Both      : Scroll down one page in the history buffer
   Scroll Wheel       : Web       : Scroll up / Down in history buffer
```
# Debug Keys:
```
   Control-d          : Dump the contents of the history & pending buffer
                        to a file for debugging
   Control-r          : Reload muddler's perl code if there are any changes.
                        without dropping connections.
```
# Supported Commands:
```
   /version           : Show the current version information for muddler.
   /world <world>     : Connect to the specified world as defined in the
                        .tfworlds file.
   /listsockets       : List currently open worlds.
   /quit              : Quit muddler
   /reload            : Reload muddler's perl code if there are any changes.
                        without dropping connections.
   /recall <cnt> <pat>: Recall <cnt> lines matching <pattern> from the
                        current world's history. 
   /help [<topic>]    : Online help command
   /web <on/off>      : Enable the web/websocket interface
   /web_port <port>   : Change the web/websocket port. THe port specified
                        will be that of the web server. The websocket server
                        will be one port number higher.
   /def               : Define text to be gagged
   /listdef           : List defines
   /ps                : List currently running processes
   /kill <pid>        : Kill a currently running process
   /repeat <args>     : Runs a command at a specified interval
   /echo <text>       : Echo text to the screen
```
# Command line:
```
   ./muddler <options>

       --noconsole     : disable the text based console and enable the
                         web/websocket server.
       --password      : specify the password for the websocket interface.
       --port          : specify the port for the web server. The websocket
                         server will be one port number higher.
```
