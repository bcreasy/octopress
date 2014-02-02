---
layout: post
title: "An Android Phone, Part 2"
date: 2014-02-02 12:00
published: true
comments: true
categories:
- Android
- Phones
- iPhone
- Technology
- Hardware
- FOSS
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

The instructions for installing Cyanogenmod to the GT-i9190 device can be found [here](http://wiki.cyanogenmod.org/w/Install_CM_for_serrano3gxx).  I followed them with a few additional steps.

I'm using a modified version of Cyanogenmod.  I've applied patches using the [Auto-Patcher Tool](http://forum.xda-developers.com/showthread.php?t=1719408) for what's called OpenPdroid which allows for low-level security settings on a per-process basis.  Each app you install to an Android phone has a list of permissions you have to allow in order to use the app.  For example, an app that has nothing to do with telephone features might want access to your contact list and recent call history for some reason.  OpenPdroid lets me block those permissions for each app.  So before installing Cyanogenmod, I needed to apply the patch and repackage the installer.  

Before the phone arrived, I bought a nano-&gt;micro SIM card adapter so that I could just swap my SIM card from my iPhone 5 to this phone without having to get a new one.  By not getting a new SIM card that's the proper size for the S4 Mini, I'm able to, if I choose, switch back to using my iPhone 5 without any issue.  I also bought a 64gb sdcard for expanded storage.  The S4 Mini comes with 8gb of built-in storage and, while this is probably sufficient for my use, I want to be able to store my data on removable storage.  I like to think of it as having a separate /home partition so I can reformat and reinstall the OS without losing my important data.

When the phone arrived, I unboxed it and powered it on without a SIM card or sdcard to verify that it boots and to go through the initial configuration without having it phone home during that process.  After getting it to the home screen, I shut the phone down and rebooted it with the SIM card to verify cell connectivity; I wanted to make sure the SIM card actually worked before wiping the phone.

With SIM card connectivity verified, I shut it down and removed the SIM card once again.

To install any custom ROM, you need an unlocked bootloader which this phone has.  Because of that, I'm able to install a "Recovery Mod" called ClockworkMod which is what allows you to wipe the device clean and install a custom ROM.  Think of it as a more powerful LILO or Grub.  After booting into ClockworkMod, I wiped all parts of the device to get rid of Samsung's default garbage and installed my OpenPdroid patched version of Cyanogenmod 10.1.3.1.

Remember, at this point, I'm still without a SIM card in place.  This is because Android/Cyanogenmod is going try to phone home and talk to Google.  I don't want it to do that before I have a chance to configure OpenPdroid and a firewall.

### Configuring OpenPdroid and AFWall+

To install the OpenPdroid configuration app and AFWall+ without a functional network connection in place, I had to "sideload" the apps via a USB adb(1) connection.

After these are installed, I set the firewall up for blacklist mode where app connectivity is whitelisted by default and I select which I want to block.  I set most of the system service apps to pass and blocked all of the default userland apps since I don't plan on using ones such as the default email client and web browser. I configured apps in OpenPdroid a similar way by blocking apps from being able to access contacts, call log, network info, etc.

My approach to using OpenPdroid is to blacklist permissions for everything to begin with and open things up as I find they don't work how I need them to.

### F-Droid Apps

I try to avoid using Google's Play store as much as possible when installing apps.  Instead, almost all of the apps I have installed came from the [F-Droid Store](https://www.fdroid.org), a collection of Free and Open Source Software available for the android platform.  All of the apps in f-droid are curated by a community of people who keep a close eye on app licenses, source code availability, and make note of any anti-features (adverts, tracking, non-free dependencies).  The goal is to use as much Free and Open Source software as possible.

Cyanogenmod itself comes bundled only with Free and Open Source apps, so many of the general uses are already covered from the get-go.  Here are apps I have installed through F-Droid:

* [AFWall+](https://f-droid.org/repository/browse/?fdfilter=afwall&fdid=dev.ukanth.ufirewall) - Software firewall
* [APG](https://f-droid.org/repository/browse/?fdfilter=apg&fdid=org.thialfihar.android.apg) - PGP keyring
* [Bitcoin](https://f-droid.org/repository/browse/?fdfilter=bitcoin&fdid=de.schildbach.wallet) - Bitcoin wallet
* [ConnectBot](https://f-droid.org/repository/browse/?fdfilter=connectbot&fdid=org.connectbot) - SSH client
* [Firefox](https://f-droid.org/repository/browse/?fdfilter=firefox&fdid=org.mozilla.firefox) - Web browser
* [Hacker's Keyboard](https://f-droid.org/repository/browse/?fdfilter=hacker&fdid=org.pocketworkstation.pckeyboard) - Full-featured keyboard, used with connectbot
* [K-9 Mail](https://f-droid.org/repository/browse/?fdfilter=k-9&fdid=com.fsck.k9) - Mail client
* [Tomdroid](https://f-droid.org/repository/browse/?fdfilter=tomdroid&fdid=org.tomdroid) - Note taking software
* [VLC](https://f-droid.org/repository/browse/?fdfilter=vlc&fdid=org.videolan.vlc) - Video player

There are a handful of apps that I installed through the Play store, however:

* [App Quarantine](https://play.google.com/store/apps/details?id=com.ramdroid.appquarantine) - Quarantine apps, used for things like Google Apps
* [BitTorrent Sync](https://play.google.com/store/apps/details?id=com.bittorrent.sync) - Encrypted, distributed backup solution
* [Google Authenticator](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2) - Two-factor authentication
* [Facebook](https://play.google.com/store/apps/details?id=com.facebook.katana) - Facebook

I've also installed, as my twitter client, [Falcon Pro](http://getfalcon.pro), which is not open source, but is made freely-available as a plain .apk file outside of app stores.

Through the App Quarantine app, I've disabled all of the default apps where I prefer to use a third party one.  Examples of this would be email and web browser.  I also disabled any app that I have no interest in ever using like a movie editor or voice dialer.

### Google Apps

Unfortunately, because I want to be able to view my work calendar on my phone and get calendar alerts, I had to install Google Apps.  This means I got all the stuff that comes with that like Google Plus and Gmail clients as well as contact syncing.  So I just blacklisted and quarantined the hell out of all the apps and services that were installed along with it with the exception of calendar syncing.

### Backups

I perform automatic encrypted torrent-based backups on both my external sdcard and internal sdcard (userland only) using [Bittorrent Sync](http://www.bittorrent.com/sync).  The backups go to my own private servers and only happen over wifi connectivity.  This means aside from data in motion, I have complete control over all aspects of my data.

### Conclusion

As you can see, I put a little bit of effort into customizing my phone to my needs.. and my needs aren't much, as I focused on in [Part 1](/log/2013/11/07/an-android-phone/).  Full-disk encryption aside (which I should probably do at some point), I also focused on making my device secure and private while keeping it as useful as I need it to be.  I encourage you to do the same.
