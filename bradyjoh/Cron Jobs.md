###1.
    15 22 * * 3 touch /tmp/dummy
    0 4 * * 6 rm /tmp/dummy

###2 
Thanks to [this](http://www.nixtutor.com/linux/sending-email-alerts-through-cron/) link for helping me find info on mailing. With this, I can see we could make a crontab command which will automatically send email to whoever's email is in the 'MAILTO' variable, or we could add a 'mail' command that the output gets piped to. 
    @monthly du -h /var/mail/stone | mail "File Size" stone@cs.grinnell.edu

###3
First type 'at now +5 hours' to get into the AT file, and then type the command: 'cat /tmp/newlog >> /tmp/archive' and signal a disconnect/EOT to close the AT file: '^D'