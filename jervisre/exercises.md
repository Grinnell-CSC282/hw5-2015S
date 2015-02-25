0.  Write a cronfile to create empty /tmp/dummy file at 10:15 pm every 
    tuesday and delete it at 4am on Saturday.

-> create a crontab with 'crontab -e' command
body:

15 22 * * 2 touch /tmp/dummy
0 4 * * 6 rm /tmp/dummy


1. Write a cronfile that will determine the size of a sile named
 /var/mail/stone at midnight on the first day of each month and mail
the result to stone@cs.grinnell.edu

@monthly stat /var/mail/stone > mail -s 'Size of /var/mail/stone' stone@cs.grinnell.edu



2. Issue an at command to append the contents of a file named /tmp/newlog
to an already existing file named /tmp/archive five hours from now

at now"+5hours" cat tmp/newlog >> /tmp/archive
