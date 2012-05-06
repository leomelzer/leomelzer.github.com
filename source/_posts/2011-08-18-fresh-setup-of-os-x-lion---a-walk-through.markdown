--- 
title: Fresh Setup of OS X Lion - a walk-through
comments: true
layout: post
---

Setting up my MacBook Pro with a fresh install of Mac OS X Lion - a brief walk-through. ~

I'd like to do a *fresh* reinstall, which means I'll wipe the disk.

# First things first: *What do I need to backup?*
Turns out it's not that much in 2011, especially for my Laptop which I use as a secondary machine only. Good place to start is the personal `Users` folder.

- I like to keep my **Desktop** empty, so nothing here to save
- **Documents** is symlinked into my Dropbox, so nothing to save here as well
- **Downloads**: had some misc stuff here, turned out it all could be deleted
- **Dropbox**: Okay, this is important. But it's in the Cloud anyway. So: next!
- **Movies, Pictures & Music**: I currently don't have actual files on my Laptop, only on the iMac, so nothing to save here (Note for Pictures: PhotoBooth saves its Library in a separate file in there, there wasn't anything of value for me, but you might have to check)
- **Custom Folders**: I keep a *Code* Directory in my Users folder. But browsing through the contents reassured me, they are either cloned public GitHub repositories, thus can be retrieved at any time, or are private repositories. Just ran a quick `git status` to make sure there are no unsynced changes.

_Looking good!_

# Next up: *Applications*!
Might as well do some clean up along the way and abolish never-used Apps&hellip;let's open _AppCleaner_.

- first victim: **Adium**. You served me well but iChat is just too nice, especially since I don't need all that multi-messenger stuff anymore - Jabber ftw!
- **Eclipse**: you served me well, too. But as long as I don't need to do Java-y stuff I'd rather keep you outta here.
- **Flickr Uploadr**: Hardly ever used you, the UI needs a major makeover&hellip;and the web-interface is just fine.
- **R**: You are cool, but our University course on Analysis & Visualization is over.
- **Scribo**: Textmate works great as a Latex Editor, though I might get back to you.
- **TrailRunner**: Hardly ever used you.
- **BetterTouchTool**: I'll try without you, Apple finally improved the multi-touch settings in Lion. Not sure this will be a permanent decision.
- **OpenOffice**: This will be interesting. Recently purchased Pages.app in the AppStore so I have this aspect covered already. I'll try to use Google Docs for everything else.
- **Xbench**: I already know my SSD is pretty fast. Just ran a quick check to see if this is still the case on year later and yes, good results - even a tad better then the last time I ran it. Thank you.

Cool, this alone cut down the list by 9 entries and freed 867 MB disk space (I don't have that much to waste with my 50 GB SSD).

Let's quickly check the other Tabs in AppCleaner.app:

- **Widgets**: DeliveryStatus is the only thing I care about.
- **Others**: AppCleaner lists media-conversion components here, as well as custom Preference Panes. *Perian*, *Growl* are there to last.

Let's save what we have as screenshots:
[Applications I](http://cl.ly/9H3D), [Applications II](http://cl.ly/9Hl6)

2011 - the year of the AppStore. It's possible to re-download all Applications without fuzz but let's take a screenshot to know which were actually installed:
[AppStore Installs](http://cl.ly/9HFk)

# Keychain & SSH
Forgot this once and while it was not too hard to recover the lost credentials I wanted to get this right this time.
Turns out your keychain is located in `~/Library/Keychains/` - the file is probably called `login.keychain` but there may be more - just backup them all. Reference: [Apple Knowledge Base](http://support.apple.com/kb/ht2980) (though this is for 10.4 it's still the same).

Okay, great. So what's (purposely) missing?

- **All things Browser-related**: I sync Google Chrome with my Google Account so I'm safe here. 
- **Dropbox**
- **Settings**: I'd like to start with a blank slate and build up from there. May be different for you.
- **Contacts & Events**: Yep, in my Google Account.
- **Printers**: I'll have to set them up once again, not sure if you can properly "export" them but I don't really mind.
- **Drivers**: there are none. YES!

Great, looks like we are nearly ready to go. But&hellip;let's run a quick `ls -la` in ~ to check what's hidden there&hellip;

I don't care for the various dotfiles which got stuck here over time - as said before, I'd like to start with a blank slate. But I *do* mind `~/.ssh` however! Let's back that up and save it in a secure place (that is, not in Dropbox). 

Cool. I'll save the passphrase for my current Wifi somewhere so I don't have to actually stand up and walk down and look for a cable or check the password on the router before the first sync with everything cloudy.

Let's restart in Recovery Mode (by pressing *&#x2318;+R* on startup) and try to install some fresh Lion. See you in a minute.

**(Snap! Turns out it took me a bit longer, it's 18th August now)**

Oh well. The problem which took me a while to figure out was the Firmware Password I set on my Macbook Pro about a week ago, along with the installation of [Prey](http://preyproject.com/). I'll save this issue for a dedicated blog-post&hellip;

# Fresh Install - Partitions

In order to have a truly fresh install I created a separate partition and installed 10.7 on there. Afterwards I deleted the old OS and merged the partitions again. Simply running *Install* will only upgrade your old OS. 

# Up & Running

1. Google Chrome, setting up Sync
2. Dropbox, starting Sync
3. *AppStore*: XCode, Pages, MPlayerX, CloudApp, Caffeine, Soundcloud, The Unarchiver, Twitter
4. *Download & Install*: [1Password](http://agilebits.com/products/1Password/Mac), [Mailplane](http://mailplaneapp.com/), [PeepOpen](http://peepcode.com/products/peepopen), [Pixer](http://www.1802.it/pixer.php), GitHub, [Arq](http://www.haystacksoftware.com/arq/), [Alfred](http://www.alfredapp.com/), Textmate, Firefox, [TaskPaper](http://www.hogbaysoftware.com/products/taskpaper), Skype, [Sequel Pro](http://www.sequelpro.com/), VirtualHost X, Perian Preference Pane, Growl, [AppCleaner](http://www.freemacsoft.net/#), [Prey](http://preyproject.com/), [TotalTerminal](http://totalterminal.binaryage.com/)
5. Install [brew](https://github.com/mxcl/homebrew) and [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh), enabling some Plugins
6. *brew*: MacVim, rvm, wget
7. Move my Dock to the left, decrease Magnification
8. Remove extraneous Icons from the Dock / Finder Sidebar, solid Menubar-Background
9. Running Software Update
10. Turning on the Firewall & File Sharing
11. Wiring up 1Password and Dropbox, installing Browser Extensions for Dropbox
12. Setting up my Google Account in *Mail, Contacts & Calendars*
13. Setting up my Google Account with *Address Book* (why is this not the same&hellip;?)
14. Getting familiar with the *Trackpad* Settings
15. Setting up Wallpaper Rotation
16. Setting up Prey, testing Reports
17. Creating `~/Code` and checking out my private Repositories in there
18. Enabling PHP5 in `/private/etc/apache2/httpd.conf` & restart Apache
19. Restoring `~/.ssh` form my Backup

I didn't install all the Applications I had before and will just install them when necessary.

Less then 20 steps for a fresh and slightly customized system. Gone are the days of juggling with multiple CDs and driver installations and stuff. You'd be screwed without broadband though.

21.6 GB still free on my SSD. Feels snappy!

# Problems

When installing brew on Lion, use a modified [install-script](https://raw.github.com/gist/1140207) to avoid problems when running `brew update` (Reference, [Issue 6886](https://github.com/mxcl/homebrew/issues/6886)).

Other than that, I didn't run into serious problems caused by 10.7 - looks like all Developers took care of compatibility before the release.

# Do it!

Upgrade if you haven't yet. This post doesn't focus on all the nice small improvements in Lion but I think Apple delivered a good Update - no revolution - but reasonable additions, needed improvements & some really nice UI-refinements.
Exciting times, the roll-out of iCloud will certainly make some of Lions hidden features more apparent.

Phew, you made it this far? A rather boring and imageless post but maybe you found a tidbit or two which helped you improve your setup. Get [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) and [TotalTerminal](http://totalterminal.binaryage.com/) if you use the command line more than once a day. Feel free to share additions in the comments!
