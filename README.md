#App::Alice
an Altogether Lovely Internet Chatting Experience

##SYNPOSIS

  arthur:~ leedo$ alice

  You can view your IRC session at: http://localhost:8080/view

##DESCRIPTION

Alice is an IRC client that can be run either locally or remotely, and
can be viewed in multiple web browsers at the same time. The alice server
stores a message buffer, so when you load your browser you will get
the most recent 100 lines for each channel. This way you can close the 
web page and continue to collect messages to be read later.

Alice's built in web server maintains a long streaming HTTP response
to each connected browser. It uses this connection to push IRC messages
to the browsers in realtime. Sending messages and events to a channel
is done through a simple HTTP request back to the alice server.

##USAGE

After installing, there should be a new `alice' command available. Run
this command to start the alice server. The first run won't find
a config file (~/.alice.yaml), so it won't be connecting to any
IRC servers. Open your browser and connect to the URL that was printed
to your terminal (probably http://localhost:8080/view). You will see a
small icon in the bottom corner; this button will bring up the connection
configuration window. Add your IRC servers and channels in this window
and save. This will get you connected to those servers, and your channels
should appear as tabs at the bottom of the screen.

##COMMANDS

###/join $string

Takes a channel name as an argument. It will attempt to join this channel
on the server of the channel that you typed the command into.

###/part

This will close the currently focused tab and part the channel. Only works on
channels.

###/close

Closes the current tab, even private message tabs. If used in a channel
it will also part the channel.

###/clear

This will clear the current tab's messages from your browser. It will also 
clear the tab's message buffer so when you refresh your browser the messages 
won't re-appear (as they normally would.)

###/query $string

Takes a nick as an argument. This will open a new tab for private messaging
with a user. Only works in a channel.

###/whois $string

Takes a nick as an argument. This will print some information about the
supplied user.

###/quote $string

Sends $string as a raw message to the server.

###/topic [$string]

Takes an optional topic string. This will display the topic for the current tab.
If a string is supplied, it will attempt to update the channel's topic.
Only works in a channel.

###/n[ames]

This will print all of the nick's in the current tab in a tabular format.

###/me $string

Sends $string as an ACTION to the channel

##NOTIFICATIONS

If you get a message with your nick in the body, and no browsers are
connected, a notification will be sent to either Growl (if running on
OS X) or using libnotify (on Linux.) Alice does not send any notifications
if a browser is connected (the exception being if you are using the Fluid
SSB which can access Growl). This is something that will probably become 
configurable over time.

##RUNNING REMOTELY

Currently, there has been very little testing done for running alice
remotely. So please let us know how your experience with it is.

##MOBILE INTERFACE

Surprisingly, alice works very well in Mobile Safari (the browser used
by the iPhone.) It still needs a little work to be fully functional, though.
The required style changes are automatically applied for mobile devices.

##AUTHORS

Lee Aylward <leedo@cpan.org>

Sam Stephenson

Ryan Baumann

##COPYRIGHT

Copyright 2009 by Lee Aylward <leedo@cpan.org>

This program is free software; you can redistribute it and/or modify it
under the same terms as Perl itself.