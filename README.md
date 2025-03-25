![Screenshot](screenshot.jpg)
Three windows are displaying a connection to 8bit and Parlor via Firefox, a remote session, and the original instance of muddler. The foremost window shows the world editor for 8bit. All three windows are effectively using the same connections but may show different worlds.

# muddler

Muddler is a mud client inspired by TinyFugue but with extra sprinkles. 

# Features
```
   o Console and/or web interface. Use them both if your feeling adventurous.
   o Separate Input and output areas to keep your words separated.
   o Multiple world support. Jump between worlds like a caffeinated squirrel.
   o Handy activity notifications and more pager to keep you in the loop.
   o A spell checker that turns your typos bright red.
   o Scroll backwards and forwards in time using PGUP/PGDN keys.
   o Editor for world configuration or settings
   o Support for ANSI color, UTF, Fansi, and Latin encoding
   o SSL Support for world connections and Web interface
   o Prompt support coming from worlds such as talkers / MUDS.
   o Automatically update to newest version while muddler is running
```
# Requirements
```
   You'll need Perl and some extra Perl parts. It runs on macOS, Linux and even
   Windows (with a little help from WSL, cygwin, or Strawberry Perl)

   Optional Perl parts:
      Term::ReadKey, Net::WebSocket::Server, Encode, Fcntl, Digest::MD5, Text::Aspell
      IO::Socket:SSL, IO::Select, IO::Socket, Text::ParseWords, IO::Socket::Timeout,
      Protocol::WebSocket::Client, MIME::Base64, Data::Dumper, and Time::HiRes.

      Muddler will be useable but less functional without the optional modules.
```
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
```
# Basic Commands
```
      /world or /world -e <name>
         Edit the current or specified world's connection details.
      /world <world>
         Connect to <world> or switch back to the world. Also see up/down
         arrow keys.
      /help [<command>]
         Lists all commands or provides help on an individual command.
      /quit
         Had enough, quit muddler.
      /web
         Dialog to edit the web interface settings.

         Note: If you plan to connect outside your network to muddler, the
               program uses <port> for web traffic and <port> + 1 for web-
               sockets. i.e. /port 9000 would use ports 9000 and 9001.
```
# Command Line
```
      ./muddler <options>

          --noconsole        : disable the text based console and enable the
                               web/websocket server.
          --password         : specify the password for the websocket interface.
          --port             : specify the port for the web server. The websocket
                               server will be one port number higher.
          --remote=host:port : Connect to a remote muddler session.
          --xy=x,y           : Set the screen size to x,y.
```
#  Supported Keys
```
      Key          DESCRIPTION
      Ctl-A      | Move the cursor to the beginning of the line
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
