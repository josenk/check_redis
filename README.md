Nagios check_redis script
=========================
This is a Nagios check script for redis written in python3.  There are command line arguments for a static memory usage value in MB OR memory usage percent.  Memory usage percent requires that you have `maxmemory` set in redis.conf.

Installation requirements
-------------------------
* Python3
* pip install redis

Installation
------------
```
cp check_redis <PATH_TO_NAGIOS_LIBEXEC>/check_redis
```
* Configure Nagios to use it.  (much to complicated to explain that here...  read the docs)

Command line arguments
----------------------
* --host
  * host ip or name (default: 127.0.0.1)
* --port
  * redis port (default: 6379)
* -w / -c
  * Static memory usage in MB
  * These options are NOT compatible with -W / -C
* -W / -C (default: 80, 90)
  * Percentage memory usage Warning and Critical Values.
  * You may want to raise these defaults, or use static values if you are evicting.
  * These options are NOT compatible with -w / -c


TO-DO
-----
* Add Auth
