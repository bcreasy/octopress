---
layout: post
title: "An Android Phone, Part 1"
date: 2013-10-11 14:55
published: false
comments: true
categories:
- Android
- Phones
- iPhone
- Technology
- Hardware
---
I bought a new phone: a [Samsung Galaxy S4 Mini (GT-i9190)](https://en.wikipedia.org/wiki/Samsung_Galaxy_S4_Mini).

I'm excited about this change.  It is an Android-based phone running [Cyanogenmod](http://www.cyanogenmod.org/)+[OpenPDroid](http://forum.xda-developers.com/showthread.php?t=2098156).  I decided on this phone because it: is Cyanogenmod compatible, has an sdcard slot, has a removable battery, and is a small form factor.

<!-- more -->

### Background

I'd been using an iPhone since January 2009 when I got an iPhone 3G.  From there, I got an iPhone 4 in January 2011 and then an iPhone 5 in November 2012.  I've been generally happy with the Apple ecosystem, though my interaction with it was never much.  I use iTunes to manage my master music archive at home and I use iPhoto to organize all of my photos.  However, other than that, I don't take advantage of many Apple ecosystem services.  The majority of online services I use are through Google.  Most Google services work pretty seamlessly with iOS, however, so I never really complained.

One simple comment a friend of mine made a year or so ago has stuck in my head, though.  She was in town for a conference and we met up for dinner.  I hadn't seen her in a few years and it was cool to hang out again.  But when I took out my phone (an iPhone 4 at the time), she said, "huh.. you have an iPhone... I would have expected you to have an Android phone with all sorts of custom mods."  This kept resonating in my head because she was right to be surprised because historically, I had always embraced hackable and customizable tech.  I know that the things you own don't define you, but they can definitely hint at your personality, beliefs, and lifestyle.  Plainly put, an iPhone doesn't fit with my personality.

### Android

I decided to switch to an Android-based phone for a few reasons:

First of all, I want to support the free (as in speech) and customizable environment supported by the Android operating system and its Linux kernel.  I decided to use a build of Cyanogenmod on top of the AOSP operating system.  I'm also intentionally not using the Google Play store in favor of [F-Droid](https://f-droid.org/), a 100% FLOSS app repository.

Second, I want to minimize my use of such a device and focus on its truly useful functions.

To me, a modern cell phone is four things:

1. A communication device (voice, sms, email, chat)
2. A personal organizer (calendar, reminders, notepad)
3. An information retrieval device (internet access)
4. Photo and video camera

Some will argue for having phones be able to play movies, videos, music and games.  These functions encourage distracting yourself from your environment, which I have no interest in doing.  I feel people are becoming increasingly connected all the time via their phones.  I'd rather keep my head up, talk to people, and embrace the world around me.

Lastly, I want to have more control of my privacy on my phone.  Implicitly, a cell phone tracks your location as long as it's connected to a cell network.  That part is unavoidable.  What's avoidable is the tracking done by internet services such as Google, Facebook, etc.

To accomplish this, I need to leverage the features of Cyanogenmod and two other customizations: OpenPDroid and [AFWall+](https://f-droid.org/repository/browse/?fdid=dev.ukanth.ufirewall).  OpenPDroid allows me to fine-tune application permissions to things like contact lists and gps.  AFWall+ is a iptables-based firewall that lets me block apps from being able to connect to the network over 3g, wifi, or both.  I'm also taking steps to avoid using Google and other online services in favor of storing data and information locally.  Unfortunately, I had to install Google Apps in order to be able to access my work and personal calendars.  However, I blacklist the access of all of the base Google Apps except calendar sync.

### Battery Life

A bonus for tightening down security on my phone is that my battery life is greatly extended.  So far, I've maxed out at 2.5 days of battery life on a single charge and light usage.  I could still tweak my configuration more to get it to 3-4 days.  Currently, much of the strain on my battery is due to the sketchy cell signal at work.

### Negative Aspects

(see: minor inconveniences)

* No iMessages or gtalk
* No simple media synchronization
* No mapping software -- why do I need this again?

### Conclusion

I'm happy with my new phone.  In Part 2, I go into more detail about how I have my phone set up and how I use it.
