Hacker World DoS tool
=============

Hacker World DoS tool ported to Go language from Python. 

The main difference from Python version layed in Golang architecture for concurrency: the goroutines. hackerworld.py runs
a new thread for each connection in the connection pool so it uses hundreds and thousands of threads. 
hackerworld.go just uses lightweight goroutines that used only tens of threads (commonly golang runtime started one thread for
CPU core + several service threads). This architecture allows golang version better consume resources and got much higher 
connection pool on the same hardware than Python version can.

This tool targeted for stress testing and may really down badly configured server or badly made app. Use it carefully.

Examples:

    $ hackerworld -site http://example.com/test/ 2>/dev/null

    $ hackerworldMAXPROCS=4096 hackerworld -site http://example.com 2>/tmp/errlog

Useful environment vars:

* GOMAXPROCS
  Set it to number of your CPUs or higher (no more actual for latest golang versions).
* hackerworldMAXPROCS
  Limit the connection pool (1024 by default).

More details: http://old.siberian.laika.name/node/7 

Update: well, I created this utility for one time task when I only played a bit with golang. Surprisingly I found that
this utility used by other people, got some stars on github and even included in [BlackArch Linux distro](http://blackarch.org/dos.html). So I cleaned up code a bit.

License
=======

I think it may be public domain because of it is just simple and short piece of code but for reason I don't remember already
I have choose GPL for it. Okey. So, Go version of hackerworld licensed under GPLv3. See LICENSE.

I am not related with original hackerworld utility in Python. Original hackerworld utility is authority of Barry Shteiman (http://sectorix.com). There are not any references to license in the original source then it is not under GPL. Ask author of the original utility about license. 
 

