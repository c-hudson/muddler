# muddler

   A simple perl based mudding client which should be run from a terminal.

# Ideas to Impliment:
These are things i plan to add in the furture. Most of them will be done
after the text based interface is extremely stable and usable.


```
   o websocket support   the text interface will still run but you will be
                         able to point your web browser at the client and
                         get a web based client that you can connect /
                         disconnect from. This will assume that i can "trap"
                         enough of the needed keys to make the client usable.
   o Native GUI          Axmud has a perl based Gtk3 gui. The idea will be
                         that the gui can be turned on/off as needed. The
                         terminal interface will be the only always running
                         interface (or maybe not?)
   o Scripting Language  Either impliment something tinyfugueish in nature,
                         something new, or maybe include code from teeny-
                         mush for a mush like language?
# Installation
   Download the muddler perl script. The script is currently dependant upon 's Pmc's Telnet.pm which can be found at: https://sourceforge.net/projects/perlmudclient/files/perlmudclient/pmc%202.7/. Create a directoy named Pmc where muddler is located and place the Telnet.pm in this directory.
# World Support
   Worlds may be defined in your ~/.tfworlds directory. Currently the
format of the file is exactly the same as tinyfugue's.
# Supported Keys:
```
   Arrow Right & Left : Move one character in the buffer
   Arrow Up and Down  : Cycle to the next connected world.
   Escape-w           : Move to next active world
   Control-w          : Delete previous word
   Control-P          : Move down in the keyboard history
   Control-N          : Move up in the keyboard history
   Tab                : Move forward one screen full of text if the world is
                        paused by "more".
   Control-l          : Redraw the screen
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
   /world <world>     : Connect to the specified world as defined in the
                        .tfworlds file.
   /quit              : Quit muddler
   /reload            : Reload muddler's perl code if there are any changes.
                        without dropping connections.
   /dc                : Nothing yet.. not sure why this was added.
```
