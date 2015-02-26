# Cron Stuff

#### Write a cronfile that will create an empty file named `/tmp/dummy` at 10:15 p.m. every Tuesday and delete the file with that name at 4 a.m. every Saturday. [Man page for `crontab`].

```Bash
15 22 * * 2 touch /tmp/dummy
```

#### Write a cronfile that will determine the size of the file named `/var/mail/stone` at midnight on the first day of each month and mail the result of that determination to `stone@cs.grinnell.edu`. [Source for file size], [Man page for `mail`].

```Bash
0 0 1 * * stat -c%s /var/mail/stone | -s "mail folder size cron update" "stone@cs.grinnell.edu"
```

#### Issue an `at` command to append the contents of a file named `/tmp/newlog` to an already existing file named `/tmp/archive` five hours from now. [Source for appending files], [Man page for `at`].

```Bash
at + 5 hours cat /tmp/newlog >> /tmp/archive
```

[Man page for `crontab`]:http://man7.org/linux/man-pages/man5/crontab.5.html
[Source for file size]:http://www.linuxquestions.org/questions/programming-9/file-size-using-bash-script-410766/
[Man page for `mail`]:http://linux.die.net/man/1/mail
[Source for appending files]:http://stackoverflow.com/questions/13181725/bash-append-file-contents-to-the-bottom-of-existing-file
[Man page for `at`]:http://linux.die.net/man/1/at
