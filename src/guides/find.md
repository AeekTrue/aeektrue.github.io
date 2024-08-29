`find /dir/path -name filename.txt`

**Filters: **
``` sh
-iname # case insensetive
-type # f | d | l
-perm
-empty
-user
-group
```

To find all the files which are modified more than **50** days back and less than **100** days.

`find / -mtime +50 –mtime -100`
