---
layout: post
title: "irssi SILC plugin on FreeBSD"
date: 2003-03-16 02:10
comments: true
categories: [Server, FreeBSD, SILC, Irssi]
---
*compiling irssi-0.8.6.CVS with SILC support:*

upon setting up silc.caffeine.nu (using silc protocol, not irc), the need for a good silc client to use was apparent.  fortunately, i didn't need a new client.  just a plugin for my current client, irssi.  i found a good page that has [good instructions on how to build it](http://www.penguin-breeder.org/silc/).  unfortunately, these instructions if followed exactly don't work for freebsd boxen.  so, now is the time that i play the role of freebsddiary.org and show what i did to get it compiled good.

first, i'll assume that you've already looked at the site that has the original instructions for compiling the plugin and that you've already checked out the latest irssi cvs source.  make sure you have the sources to silc-client, silc-plugin, and irssi all sitting in the same directory.

go into the silc-client directory and do `./configure --enable-ipv6 --without-irssi --enable-debug --without-iconv --without-pthreads`.  then do `gmake` to compile it.  also, make sure you have /usr/ports/devel/automake/ and /usr/ports/devel/autoconf/ both installed or else it might give you some errors. note: you don't have to install this.

next, go into the silc-plugin directory and run `./configure --with-irssi=/usr/home/genetik/cvs/irssi/ --with-silc=/usr/home/genetik/cvs/silc-client-0.9.11/ --without-threads --without-libiconv`.  adjust your paths appropriately.  now go ahead and do a `gmake CFLAGS="-g -O2"`.  if it complains at you about -liconv, you'll have to edit your Makefiles.  just search through the Makefiles for "iconv" and get rid of any instance of it.  after it finishes compiling, go ahead and do a `gmake install`.  after that, go build and install irssi.cvs.

after starting up irssi.  you'll need to run /load silc.  at this point, it'll ask you for a passphrase for your public and private keys to be generated.  after it generates them, go ahead and /connect to a silc server of your choice.  if you need one to test it on, use silc.caffeine.nu.  it runs on port 706 if you need to know for a firewall or something.

enjoy.
