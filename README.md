![Screenshot](screenshot.jpg)
Three windows are displaying a connection to 8bit and Parlor via Firefox, a remote session, and the original instance of muddler. The foremost window shows the world editor for 8bit. All three windows are effectively using the same connections but may show different worlds.

# muddler

Muddler is a client for connecting with text based MUDs. A console and web interface provide a seperate panels for keyboard and world output to
interact with one or more MUDs. Its primary purpose is to be an improved but visually similar version of Tinyfugue.

# Key Improvements
```
   o Dialog editor for many key commands instead of complex commands
   o Optional Web Interface for phone or browser use
   o Integrated input spell check
   o 256 Color, UTF8, Fansi, Latin Support
   o Multiple Window support via multiple terminals and websockets
   o Activitly developed

# Similarties
```
   o Support of many Tinyfugue commands
   o Connect to Multiple worlds at the same time
   o Input and Output pane to keep your typing seperate from MUD output
   o Visually the same interface as TinyFugue on console and via the web.
     I.e. Input / output window panes for keyboard and MUD output
   o Internal /help Command
   o Pausable output to control output
   o History buffer scrolling via PGUP/PGDOWN keys

# Supported Platforms
```
   muddler runs on almost anything that supports Perl. The list of
   supported platforms is due more to Perl then say good coding on my
   part.

   o Windows via WSL
   o Android via Termux
   o Drobo NAS
   o More standard UNIX plantorms (Linux/NetBSD/etc)
   o The Web interface can be viewed on any browser


```
# muddler goals
```
   o Simplicity. A MUD client should be simple to use.
   o Aid users in switching between computers/phones without loosing
     connectivity.
   o Waste time writing code few will use. We're not in 1990 any more.
   o Simple installation  [its a goal, not a feature]
   o Improvements - Find a bug or something you don't like, I'll make
     it my challenge to fix it or improve upon the issue.

# References
```
   MUDs: https://en.wikipedia.org/wiki/Multi-user_dungeon
   TinyFugue: https://tinyfugue.sourceforge.net/

# Installation
```
   The below install steps are for a Linux system. Please see the specialized
   instructions for specific environment included in the respository.

   a. download muddler script
   b. chmod u+x muddler
   c. Install required perl modules manually. Muddler will tell you wich
      modules are missing.

         or 

      ./muddler --install

         This will install missing modules and/or install the modules from
         cpan. Currently this only works on linux systems supporting apt.

   d. ./muddler <options>

   Options:
      --noconsole        : disable the text based console and enable the
                           web/websocket server.
      --password         : specify the password for the websocket interface.
      --port             : specify the port for the web server. The websocket
                           server will be one port number higher.
      --remote=host:port : Specify the remote muddler websocket host/port
                           to connect to.
```
# Quick Start
   
```
   Basic Commands:
      /world
         Edit the current world's connection details.
      /world <world>
         Switch the current world to <world>. Muddler will open up a
         new connection if needed. Switching between existing worlds
         can also be done with the up/down arrows and escape-w.
      /help [<command>]
         Lists all commands or provides help on an individual command.
      /quit
         Had enough, quit muddler.
      /web
         Dialog to edit the web interface settings.

         Note: If you plan to connect outside your network to muddler, the
               program uses <port> for web traffic and <port> + 1 for web-
               sockets. i.e. /port 9000 would use ports 9000 and 9001.

   Command Line:
      ./muddler <options>

          --noconsole        : disable the text based console and enable the
                               web/websocket server.
          --password         : specify the password for the websocket interface.
          --port             : specify the port for the web server. The websocket
                               server will be one port number higher.
          --remote=host:port : Connect to a remote muddler session.
          --xy=x,y           : Set the screen size to x,y.

   Supported Keys:

      Keys         DESCRIPTION
      Ctl-A      | Move the cursor to the begining of the line
      Ctl-E      | Move the cursor to the end of the line
      Ctl-L      | Erases the screen and redraws it
      Ctl-N      | Moves forward one entry in the keyboard history.
      Ctl-P      | Moves back one entry in the keyboard history.
      Ctl-R      | Reloads the code for muddler if there are any changes
      Ctl-U      | Clears the keyboard input
      Ctl-W      | Delete the last word before the cursor
      Down       | Switch to world with activity, or cycle down through connected worlds.
      Esc-J      | Skip to the end of any "mored" output.
      Esc-Q      | Show spell suggestions for last word. Cycle thru on next esc-q
      Esc-W      | Go to the next active world, or the last world
      Esc-Esc    | Quick exit out of the world editor
      Pgdn       | Moves forward in the history of the current world
      Pgup       | Moves back into the history of the current world
      Tab        | Moves forward a screen full when more is enabled/triggered.
      Up         | Switch to world with activity, or cycle up through connected worlds.
      Shift Up   | Cycle through all worlds (connected or disconnected)
      Shift Down | Cycle through all worlds (connected or disconnected)
