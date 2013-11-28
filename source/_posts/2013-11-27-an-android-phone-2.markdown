---
layout: post
title: "An Android Phone, Part 2"
date: 2013-11-27 18:02
published: false
comments: true
categories:
- Android
- Phones
- iPhone
- Technology
- Hardware
---
My new cell phone, a [Samsung Galaxy S4 Mini (GT-i9190)](/log/2013/11/07/an-android-phone/), runs Android 4.2.2, but I've installed a custom distribution called [Cyanogenmod](http://www.cyanogenmod.org) and made modifications/tweaks to make it more secure.

<!-- more -->

### Goals

1. Use Cyanogenmod instead of either Samsung's bloatware garbage distribution or stock Android
2. No automatic "cloud" synchronization of data
3. Obtain locational privacy at the service level
4. Use only Free/Libre Open Source Software where possible
5. Avoid using Google apps/services or the Play store

### Installing Cyanogenmod

I chose Cyanogenmod for a few reasons: First of all, being it's completely Free (as in speech) and includes no proprietary software.  It's also the most widely used Android ROM, so it's well-supported on my device and kept very up to date with current Android versions.

However, I'm using a modified version of Cyanogenmod.  I've applied patches for what's called OpenPdroid which allows for low-level security settings on a per-process basis.  Each app you install to an Android phone has a list of permissions you have to allow in order to use the app.  For example, an app that has nothing to do with telephone features might want access to your contact list and recent call history for some reason.  OpenPdroid lets me block those permissions for each app.  So before installing Cyanogenmod, I needed to apply the patch and repackage the installer.

Before the phone arrived, I bought a nano-&gt;micro SIM adapter so that I could just swap my SIM card from my iPhone 5 to this phone without having to get a new one.  By not getting a new SIM that's the proper size for the S4 Mini, I'm able to, if I choose, switch back to using my iPhone 5 without any issue.  I also bought a 64gb sdcard for expanded storage.  The S4 Mini comes with 8gb of built-in storage and, while this is probably sufficient for my use, I want to be able to store my data on removable storage.  I like to think of it as having a separate /home partition so I can reformat and reinstall the OS without losing my important data.

When the phone arrived, I unboxed it and powered it on without a SIM or sdcard to verify that it boots and to go through the initial configuration without having it phone home during that process.  After getting it to the home screen, I shut the phone down and rebooted it with the SIM card to verify cell connectivity; I wanted to make sure the SIM card actually worked before wiping the phone.

With SIM connectivity verified, I shut it down and removed the SIM once again.

To install any custom ROM, you need an unlocked bootloader which this phone has.  Because of that, I'm able to install a custom bootloader called ClockworkMod which is what allows you to wipe the device clean and install a custom ROM.  Think of it as a more powerful LILO or Grub.  After booting into ClockworkMod, I wiped all parts of the device to get rid of Samsung's default garbage and installed my OpenPdroid version of Cyanogenmod 10.1.3.

Remember, at this point, I'm still without a SIM.  This is because Android/Cyanogenmod is going try to phone home and talk to Google.  I don't want it to do that before I have a chance to configure OpenPdroid and a firewall.
