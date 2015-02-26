# Exercises using the 'cron' command
## 0.

15 22 * * 2 touch /tmp/dummy

0 4 * * 6 rm /tmp/dummy

## 1.

@monthly du /var/mail/stone | mail -s "Size of /var/mail/stone" stone@cs.grinnell.edu

Source(s):
[Mail command](http://stackoverflow.com/questions/4658283/shell-script-to-send-email)

## 2.

at now + 5 hours

at> cat /tmp/newlog > /tmp/archive
