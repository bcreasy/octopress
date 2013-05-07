---
layout: post
title: "apache doom"
date: 2004-08-16 01:07
comments: true
categories: 
---
all i wanted to do was add the halcyonhosting.net virtualhost to apache, restart it, and go to sleep. nayuki disagreed...

<!-- more -->

so celeste and i decided upon a name for our hosting business: Halcyon Hosting. so i bought it through godaddy, added the nameserver zone, added postfixadmin entries, added the virtualhosts to apache. went to restart apache. boom. segfault. now, i did upgrade a bunch of stuff the other day because of a perl upgrade in the ports system, but i didn't think it would affect apache. that was the first thing i thought of for a reason behind the segfault. after a good hour of "wtf'ing" and cursing apache, i deinstalled apache13-modssl and installed apache13 without ssl. perhaps it was an openssl issue that i didn't catch. when i went to start up apache with that install, it complained about a corrupt mod_php4.so.. so i commented that out in httpd.conf, ran `apachectl start' and wouldn't you know it, it didn't segfault. so that got me thinking.. maybe it's something with php4. i deinstalled apache13 and reinstalled apache13-modssl again, left mod_php4.so commented out, and it didn't segfault either. yep. php4 issue. i went straight to the new kid on the block in the ports system, extensions.ini, which contains all of the extensions that php4 loads, commented all of the extensions out, and tried apache again. it worked fine. so, i just uncommented each extension one at a time restarting apache each time until i found which one was the culprit. it turned out to be mhash.so.. i'm not really familiar with the functions that are in that library, but i also haven't ran into any problems with it not running. i guess i'll watch freebsd-ports@ for a while to see if something comes up.
