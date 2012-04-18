# FlowCopy

This is a rough version of flowcopy.  It is used to copy files across a Lan using [BitTorrent](http://www.bittorrent.com/).  It is inspired by [Twitter Murder](http://engineering.twitter.com/2010/07/murder-fast-datacenter-code-deploys.html) and uses (and includes) [BitTornado](http://www.bittornado.com/).  FlowCopy is being developed on a Mac.  With minor changes, it should work on other unices.  It does require Python 2 and bash.

## Providing Files

You need one computer to seed the file.  It will run a tracker and seed the .torrent file.

On that machine, run these commands, in different terminal windows:

    ./flowcopy_start_tracker
    ./flowcopy_host /path/to/file/to/copy/filename

## Transceiving Files

To transceive is to transmit and receive.  (Let me know if you have a better verb.  'peer' and 'get' don't quite convey what I'm after).

On your peer machines, run this command:

    ./flowcopy_transceive filename

or

    ./flowcopy_transceive filename path/to/save/file/as


## Known Issues

Currently, the client does not stop after it has downloaded the file in its entirety.

## Tweaks

I'm using settings suggested by the twitter Murder project, on the whole.  If you have some "better" settings, I'd love to hear about them.

Note that the host and transceivers are currently using curses to display the results.  You can the 'btdownloadcurses.py' part of the lines that look like:

    $PYTHON "$BITTORNADO_DIR/btdownloadcurses.py" \

to `btdownloadheadless.py` or `btdownloadgui.py`, if you like.  (Maybe there'll be a command line option in the future.)

Have fun!

