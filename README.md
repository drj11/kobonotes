Kobo Mini
=========

Enabling telnet
===============

TelnetEnabler.zip from here: http://www.mobileread.com/forums/attachment.php?attachmentid=108297&d=1373983679

unzip; it contains a file called `KoboRoot.tgz`. Copy
`KoboRoot.tgz` into the `.kobo` directory of your
Kobo when it is plugged into a PC as a USB drive.

Enable networking (for example, Wireless panel of the Settings
page). Get device IP from the Device Information panel of the
Settings page.

telnet; username `root`; no password.

Wireless On
===========

The `nickel` program (the main Kobo UI) will switch the wireless
off after a few minutes. Annoying.

    killall -SIGSTOP nickel  # stop execution
    killall -SIGCONT nickel  # resume it

Images
======

    zcat /etc/images/splash.raw.gz  | /usr/local/Kobo/pickel showpic

Image format is raw 16-bit LE RGB565 800x600. See
`https://github.com/drj11/pypng/blob/master/code/pngtokobo565`
for a converter from PNG to this format.

Fetching Stuff From Internet
============================

    wget -O - http://192.168.0.6:8000/golfer.raw |
      /usr/local/Kobo/ pickel showpic

`wget` doesn't seem to support `https`.

Compiling Your Own Programs
===========================

Don't know.

External Resources
==================

Many people on the internet helped:

Useufl general hackery: http://www.chauveau-central.net/pub/KoboTouch/

Hints on using ffmpeg http://www.mobileread.com/forums/showpost.php?p=1752157&postcount=1
