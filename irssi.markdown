irssi
=====

Prepare new irssi for Freenode
------------------------------
    
    /network add -nick elliottcable -user cable -realname 'elliott cable' Freenode
    /server add -auto -network Freenode chat.freenode.net
    /channel add -auto #yr Freenode
    /channel add -auto #BlipBloop Freenode
    /channel add -auto #MacOSX Freenode
    /channel add -auto #RubyNoob Freenode
    /channel add -auto #Ruby-Lang Freenode
    /channel add -auto #Ruby Freenode
    /channel add -auto #OFFrails Freenode
    /channel add -auto #GitHub Freenode
    /channel add -auto #Git Freenode
    /connect Freenode

Important channel
-----------------
Hilight all messages in the channel
    
    /hilight -channel #chan -regexp .*