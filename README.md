![Screenshot](screenshot.jpg)
# muddler

   A simple perl based mudding client which should be run from a terminal or your web browser.

# Ideas to Impliment:
These are things i plan to add in the furture. Most of them will be done
after the text based interface is extremely stable and usable.


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
   
   Arrow Right & Left : Move one character in the buffer
   Arrow Up and Down  : Cycle to the next connected world.
   Escape-w           : Move to next active world
   Control-w          : Delete previous word [console only]
   Control-P          : Move down in the keyboard history
   Control-N          : Move up in the keyboard history
   Tab                : Move forward one screen full of text if the world is
                        paused by "more".
   Control-l          : Redraw the screen [console only]
   Escape-L           : Redraw the screen [web]
   PgUp               : Scroll up one page in the history buffer
   PgDown             : Scroll down one page in the history buffer
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
