vrun
====

CLI control of VLC Media Player using the telnet interface.

A bash completion file is provided.

This offer an easy way to do collaborative playlist in CLI via ssh.


### Installation

just put vrun in your path with execution right and ```. /path/to/vrun_bash_completion``` to your .bashrc

You can overload vlc telnet port or password by creating a file :
<pre>
$ cat ~/.config/vrun/configrc
# vlc telnet port
tport=4212
#vlc telnet address
taddress="127.0.0.1"
# local vlc binding address
tbind="127.0.0.1"
# vlc telnet password
password="admin"
</pre>


### Usage

For the bash completion to fully work, a vlc instance with the telnet interface activated need to be up
or the ```~/.config/vrun/commandrc``` with a list of command need to be fill up.
Otherwise, you can only complete ```vrun start``` that will lauch an instance of vlc.

If you really want to feel up the ```~/.config/vrun/commandrc``` file (personnaly, I don't),
launch a vlc instance and run : 
<pre>echo "`vrun help \"\\*\" 2>/dev/null | sed 's/\. \. .*//;s/, /\n/g;/^+/d;s/| *//g;s/ .*//;s/\r//g'` start" > ~/.config/vrun/commandrc</pre>
it should do the tricks.

For feature list, just use tab completion or ```vrun help```, and ```vrun help command``` for description.

#### Command list
<pre>
 * add XYZ  . . . . . . . . . . . . . . . . . . . . add XYZ to playlist
 * enqueue XYZ  . . . . . . . . . . . . . . . . . queue XYZ to playlist
 * playlist . . . . . . . . . . . . . .show items currently in playlist
 * search [string]  . .  search for items in playlist (or reset search)
 * sort key . . . . . . . . . . . . . . . . . . . . . sort the playlist
 * sd [sd]  . . . . . . . . . . . . . show services discovery or toggle
 * play . . . . . . . . . . . . . . . . . . . . . . . . . . play stream
 * stop . . . . . . . . . . . . . . . . . . . . . . . . . . stop stream
 * next . . . . . . . . . . . . . . . . . . . . . .  next playlist item
 * prev . . . . . . . . . . . . . . . . . . . .  previous playlist item
 * goto, gotoitem . . . . . . . . . . . . . . . . . .goto item at index
 * move . . . . . . . . .move items from index to index in the playlist
 * repeat [on|off]  . . . . . . . . . . . . . .  toggle playlist repeat
 * loop [on|off]  . . . . . . . . . . . . . . . .  toggle playlist loop
 * random [on|off]  . . . . . . . . . . . . . .  toggle playlist random
 * delete . . . . . . . . . . . . . . . . . . . . .delete item at index
 * clear  . . . . . . . . . . . . . . . . . . . . . .clear the playlist
 * status . . . . . . . . . . . . . . . . . . . current playlist status
 * title [X]  . . . . . . . . . . . . . . set/get title in current item
 * title_n  . . . . . . . . . . . . . . . .  next title in current item
 * title_p  . . . . . . . . . . . . . .  previous title in current item
 * chapter [X]  . . . . . . . . . . . . set/get chapter in current item
 * chapter_n  . . . . . . . . . . . . . .  next chapter in current item
 * chapter_p  . . . . . . . . . . . .  previous chapter in current item

 * seek X . . . . . . . . . . . seek in seconds, for instance `seek 12'
 * pause  . . . . . . . . . . . . . . . . . . . . . . . .  toggle pause
 * fastforward  . . . . . . . . . . . . . . . . . . set to maximum rate
 * rewind . . . . . . . . . . . . . . . . . . . . . set to minimum rate
 * faster . . . . . . . . . . . . . . . . . .  faster playing of stream
 * slower . . . . . . . . . . . . . . . . . .  slower playing of stream
 * normal . . . . . . . . . . . . . . . . . .  normal playing of stream
 * rate [playback rate] . . . . . . . . . .  set playback rate to value
 * frame  . . . . . . . . . . . . . . . . . . . . . play frame by frame
 * fullscreen, f, F [on|off]  . . . . . . . . . . . . toggle fullscreen
 * info . . . . . . . . . . . . . .information about the current stream
 * stats  . . . . . . . . . . . . . . . .  show statistical information
 * get_time . . . . . . . . . .seconds elapsed since stream's beginning
 * is_playing . . . . . . . . . . . .  1 if a stream plays, 0 otherwise
 * get_title  . . . . . . . . . . . . . the title of the current stream
 * get_length . . . . . . . . . . . .  the length of the current stream

 * volume [X] . . . . . . . . . . . . . . . . . .  set/get audio volume
 * volup [X]  . . . . . . . . . . . . . . . .raise audio volume X steps
 * voldown [X]  . . . . . . . . . . . . . .  lower audio volume X steps
 * adev [X] . . . . . . . . . . . . . . . . . . . .set/get audio device
 * achan [X]  . . . . . . . . . . . . . . . . . .set/get audio channels
 * atrack [X] . . . . . . . . . . . . . . . . . . . set/get audio track
 * vtrack [X] . . . . . . . . . . . . . . . . . . . set/get video track
 * vratio [X] . . . . . . . . . . . . . . . .set/get video aspect ratio
 * vcrop, crop [X]  . . . . . . . . . . . . . . . .  set/get video crop
 * vzoom, zoom [X]  . . . . . . . . . . . . . . . .  set/get video zoom
 * vdeinterlace [X] . . . . . . . . . . . . . .set/get video deintelace
 * vdeinterlace_mode [X]  . . . . . . . . set/get video deintelace mode
 * snapshot . . . . . . . . . . . . . . . . . . . . take video snapshot
 * strack [X] . . . . . . . . . . . . . . . . . set/get subtitles track

 * help, ? [pattern]  . . . . . . . . . . . . . . . . . .a help message
 * shutdown . . . . . . . . . . . . . . . . . . . . . . . .shutdown VLC
</pre>
The delete and move functions for deleting items in the playlist and move items in the playlist come this the version 2.1 RinceWind of VLC
