### 0.
For creating and deleting the /tmp/dummy file the cron

```shell
15 10 * * 2 touch /tmp/dummy
```
```shell
0 4 * * 6 rm /tmp/dummy
```

Would be what you would have in your cronfile

### 1.
For emailing Mr. Stone the size of his folder every month
your cronfile would look like

```shell
@monthly du -h /var/mail/stone | mail -s "Size of your mail folder" stone@cs.grinnell.edu
```

Learned about the mail app from http://en.wikipedia.org/wiki/Mail_(Unix)

### 2.
Finally to issue a command to append a file 5 hours from now you would first
enter

``` shell
at now + 5
```

and then once the at prompt comes up type
```shell
cat /tmp/newlog >> /tmp/archive
```

then 
```shell 
^D
``` and you are good to go
