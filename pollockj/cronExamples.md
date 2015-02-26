##CSC-282 Homework 5
February 25th, 2015
Wesley Pollock

####0. Write a cronfile that will create an empty file named `/tmp/dummy` at 10:15 p.m. every Tuesday and delete the file with that name at 4 a.m. every Saturday

```
#minute | hour | day of month | month |  day of week
15 22 * * 3 touch /tmp/dummy
0 4 * * 6 rm /tmp/dummy
```

####1. Write a cronfile that will determine the size of the file named `/var/mail/stone` at midnight on the first day of each month and mail the result of that determination to `stone@cs.grinnell.edu`


``` 
#minute | hour | day of month | month |  day of week
@monthly echo "The size of /var/mail/stone is $(ls -l /var/mail/stone | cut -d' ' -f5)" | mail -s "File Size" pollockj@grinnell.edu
```

####2. Issue an `at` command to append the contents of a file named `/tmp/newlog` to an already existing file named `/tmp/archive` five hours from now.

```
Script started on Wed 25 Feb 2015 07:51:03 PM CST
dijkstra$ at now + 5 hours
warning: commands will be executed using /bin/sh
at> cat /tmp/newlog >> /tmp/archive
at> <EOT>
job 4 at Thu Feb 26 00:51:00 2015
dijkstra$ exit

Script done on Wed 25 Feb 2015 07:51:30 PM CST
```

