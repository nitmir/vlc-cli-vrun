vrun
====

CLI control of VLC Media Player  using the telnet interface.

A bash completion file is provided.

This offer an easy way to do collaborative playlist in CLI via ssh.


### Installation

just put vrun in your path with execution right and ```. /path/to/vrun_bash_completion``` to your .bashrc

You can overload vlc telnet port or password by creating a file :
<pre>
$ cat ~/.config/vrun/configrc
# vlc telnet port
tport=4212
# vlc telnet password
password="admin"
</pre>
