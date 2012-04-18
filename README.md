
This is a rough version of flowcopy.  It is used to copy files across a lan using bittorrent.  Development is happening on a Mac; it is likely to work on other unix OS, that have Python 2, with a tiny bit of work.  Flowcopy depends on bittornado -- http://www.bittornado.com/ -- and includes it for convenience.

You need one computer to seed the file.  It will run a tracker and seed the .torrent file.

On that machine, run these commands, in different terminal windows:

./flowcopy_start_tracker
./flowcopy_host /path/to/file/to/copy/filename

On your peer machines, run this command:

./flowcopy_transceive filename

or

./flowcopy_transceive filename path/to/save/file/as


Have fun!

