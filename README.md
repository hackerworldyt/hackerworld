Hacker World DoS tool
=============

Hacker World DoS tool ported to Go language from Python. 

The main difference from Python version layed in Golang architecture for concurrency: the goroutines. hackerworld.py runs
a new thread for each connection in the connection pool so it uses hundreds and thousands of threads. 
hackerworld.go just uses lightweight goroutines that used only tens of threads (commonly golang runtime started one thread for
CPU core + several service threads). This architecture allows golang version better consume resources and got much higher 
connection pool on the same hardware than Python version can.

This tool targeted for stress testing and may really down badly configured server or badly made app. Use it carefully.

Commands:

    $ apt upgrade
    $ apt update
    $ pkg update
    $ pkg upgrade
    $ pkg install python
    $ pkg install python2
    $ pkg install git
    $ git clone https://github.com/hackerworldyt/hackerworld
    $ cd hackerworld
    $ ls
    $ python2 hackerworld.py {url}
    Example :- $ python2 hackerworld.py https://google.com/
     
