# Notes on Android, What I do, and Why I do it

[TOC]

## Preface

This guide is a quick set of notes I have typed up for setting up a fresh Android install.

Pull requests encouraged.

* This guide is not designed to be one-size-fits-all. I make many assumptions, and have designed this setup around my own infrastructure. I run NextCloud, using the  [ThornSec framework](https://github.com/privacyint/thornsec)
  * I will attempt to give alternatives where they occur to me...

* I'm assuming you're setting up a new Android phone, or have run a "factory reset".

* These instructions are for Android 10, but should also work on earlier versions. If you're running Android 6 or 7 and are unable to upgrade your phone's operating system, it's time for a new phone.

<u>**Following this guide will not suddenly mean your phone is "secure". I have not audited any of these apps, and make no claims about their efficacy or otherwise. Follow at your own risk.**</u>

## To Google, or Not To Google

This is a personal choice. For most people, adding a Google account is the safest option - so long as you follow proper password hygiene. This means there are backups of important files such as photos, and recovery options (including remote wiping).

If you want to go to extreme Google removal, either install a build without any Google apps, or with a Google replacement such as [microG](https://microg.org). That, however, is **way** beyond the scope of this guide!

I assume you're not adding a Google account to your phone (i.e. skipping the "log into Google" step on the setup wizard) - but it makes no real difference in the steps.

## Apps

### 1: [F-Droid](https://f-droid.org/)

![img](https://f-droid.org//assets/fdroid-screenshot-en.png)

*F-Droid* is an installable catalogue of FOSS (Free and Open Source  Software) applications for the Android platform. The client makes it  easy to browse, install, and keep track of updates on your device.

### 2: [NetGuard](https://github.com/M66B/NetGuard/)

<img src="https://raw.githubusercontent.com/M66B/NetGuard/master/screenshots/01-main.png" alt="NetGuard Screenshot" style="zoom: 33%;" />  <img src="https://raw.githubusercontent.com/M66B/NetGuard/master/screenshots/02-main-details.png" alt="NetGuard Screenshot" style="zoom:33%;" />

*NetGuard* provides simple and advanced ways to block access to the internet - no root required. Applications and addresses can individually be allowed or denied access to your Wi-Fi and/or mobile connection.

It does this by pretending to be a VPN, allowing it to filter which apps can and cannot use the Internet. It also allows for adblocking.

### 2.1: Advert and other malware blocking

To enable adblocking, do the following

<img src="https://raw.githubusercontent.com/M66B/NetGuard/master/screenshots/33-settings-advanced.png" alt="img" style="zoom:25%;" /> 

* Settings → Advanced options → Filter traffic to ON
  * This tells NetGuard that you want it to start advert blocking

* Settings → Backup → Hosts file Download URL
  * https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts - the [Steven Black Unified hosts file](https://github.com/StevenBlack/hosts). This is a list of advert + malware URLs, which are then able to be blocked directly on your device.
* Settings → Backup → Download hosts file
  * This downloads the latest version, and starts it working immediately

### 3: [NewPipe](https://newpipe.schabi.org/)

NewPipe is a replacement app for accessing YouTube, which amongst other things reduces the data usage of YouTube on your phone, and allows you to download video and/or audio directly to your phone.

### 4: [Signal](https://signal.org/)

Signal is an end-to-end encrypted messaging app, much like (the far more well-known) WhatsApp - in fact, WhatsApp's security uses the model from this App, and not the other way around.

The major advantage of Signal on Android is that you can *set it as your default SMS app* when you install it, for opportunistic encryption. Spread the love.

### 5: [Aurora Store](https://auroraoss.com/)

Aurora Store is an Unofficial FOSS client to replace Google's Play Store. It allows you to download and update apps without the need for a Google account.

A major advantage of Aurora Store over the Play Store is its integration with [Exodus Privacy](https://exodus-privacy.eu.org/en/), which automatically scans apps for trackers and other privacy leaks.

### 6: [Shelter](https://github.com/PeterCxy/Shelter)

Shelter is a Free and Open-Source (FOSS) app that leverages the "Work  Profile" feature of Android to provide an isolated space that you can install or clone apps into.

##### Features / Use Cases

1. Run "Big Brother" apps inside the isolated profile so they cannot access your data / files outside the profile
2. "Freeze" (disable) background-heavy, tracking-heavy or seldom-used  apps when you don't need them. This is especially true if you use apps  from Chinese companies like Baidu, Alibaba, Tencent.
3. Clone apps to use two accounts on one device

##### Caveats

Shelter is **not** a full sandbox implementation. It cannot protect you from:

1. Security bugs of the Android system or Linux kernel
2. Backdoors installed in your Android system (so please use an open-source ROM if you are concerned about this)
3. Backdoors installed into the firmwares (no way to work around this)
4. Any other bugs or limitations imposed by the Android system. (i.e.  If Android chooses to expose some information into the work profile,  there is nothing I could do about it)

### 7: [K-9 Mail](https://k9mail.github.io/)

K-9 Mail is an open source email client focused on making it easy to chew through large volumes of email

### 8: [KeePass DX](https://www.keepassdx.com/)

<img src="https://www.keepassdx.com/img/device.png" alt="device" style="zoom:50%;" />

Open Source Password Manager for Android, supports fingerprint unlocking

### 9: [Etar Calendar](https://github.com/Etar-Group/Etar-Calendar)

The application is an enhanced version of AOSP Calendar

### 10: [DAVx5](https://www.davx5.com/)

DAVx5 is an open source calendar syncing app, supporting a range of backends

### 11: [Firefox Focus](https://support.mozilla.org/en-US/kb/focus)

A minimal web browser with built-in ad blocking, anti-tracking, and fully "Private Windows" (with no memory).

### 12: [Tor Browser for Android](https://www.torproject.org/download/#android)

<img src="https://www.torproject.org/static/images/tor-browser-mobile-window/png/TBAa-onboarding@2x.png?h=ea944932" alt="img" style="zoom:50%;" />

Full build of the Tor Browser, native to Android
