**Important Note**

> The issues queu shows there have lately been critical problems reported.
> It seems as if this eyefiserver is not compatible with recent eyefi  cards and/or
> eyefi cards that did the firmware upgrade. YMMV.
> Given enough time, I may look into it. Any help is appreciated ..

> Me not responding to the issue queu resulted in this project being forked
> here https://github.com/dgrant/eyefiserver2 . Thanks David !


---


**Project Description**

Eye-Fi memory cards send pictures from digital cameras to your computer (or any machine on your network) using wifi. I use it to send pictures from my camera to my NAS. Read more about Eye-Fi at http://eye.fi/

This is a slight rework of a post of Jeff Tchang at Return Boolean True:
  * http://returnbooleantrue.blogspot.com/2009/01/eye-fi-standalone-server.html

finetuned for use with linux. All credits go to Jeff Tchang.

There is a similar project at
  * http://code.google.com/p/py-fi-server/source/browse/trunk/pyfiserver.wsgi


Starting this server creates a listener on port 59278. I use the BaseHTTPServer class included with Python. I look for specific POST/GET request URLs and execute functions based on those URLs.

Structure of this package :

```
	.
	|-- etc
	|   |-- eyefiserver.conf
	|   `-- init.d
	|       `-- eyefiserver
	|-- usr
	|   `-- local
	|       `-- bin
	|           `-- eyefiserver.py
	`-- var
	    `-- log
	        `-- eyefiserver.log
	
```
If you're familiar with linux, that basically sums it up :-)
  * unzip the tarball (its under downloads)
  * Put the stuff on the right place,
  * edit the eyefiserver.conf (your eyefi key has to go there)
  * optionally add stuff to your start-stop sequence. on debian/ubuntu, use update-rc.d:

```

sudo update-rc.d eyefiserver defaults 98 02

```

et voila.