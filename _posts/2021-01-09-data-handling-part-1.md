---
layout: post
title:  "Safe Data Storage for the Masses: Part 1"
date:   2021-01-09 15:19:56 +0200
categories: data storage cloud synchronization backup safety security idea 
---

From time to time, friends or family members ask me for recommendations how they should store and backup their data. Most people (both technical and non-technical) I know have a sense that they should be keeping their data safe, but fail to actually do so. Instead of blaming them, I think we should create systems that make safe and secure data storage so simple that everyone can easily use it. 

In this post, I first describe the options a regular (= non-technical) user has today and the problems I see with them. I'll then present my vision of how data storage should be done instead.

# Current Options

I currently see three options for data storage and backups, each having their advantages and disadvantages:

## 1. Manual

This is the "old" way. Use an external hard drive and copy everything that needs to be backed up onto the device regularly. Most operating systems contain backup programs that make it relatively easy to set this up and remind you to plug the backup drive in once in a while.

I see two big disadvantages with this approach. First of all, it doesn't fit into current device usages anymore. Back when a user's only device was a desktop computer, this was an ok-ish option, but nowadays people own multiple devices. Sure, one could manually copy all data from all devices (smartphones, tablets, computers, cameras, ...) onto a single device and then do backups of that device, but that's not practical from what I've seen. This brings me to the second disadvantage of this approach: User-laziness. People don't want to loose data, but manually doing backups requires time and if you don't do it, there's still a pretty high change that you'll be fine. So people (including me) tend to simply not do such work.

## 2. The Cloud

The second option is to use some sort of cloud storage. Dropbox, Google Drive, iCloud, you name it. The obvious advantage of this approach is it's user-friendliness. Simply create an account, download the apps and upload your data. This gives you a single space for your data that can be accessed from all of your devices.

But once again, I see problems with this approach. The first one is that users are giving their data out to some big company. You don't know where they're storing your data, who's going to have access to it and what they're going to do with it. In many cases, these cloud storages are also part of a larger platform trying to lock you in. The most successful example here probably is Apple. iPhone users usually use iCloud because it's so convenient. If they run out of space on the free plan, they'll buy additional iCloud storage without even considering alternatives. Once you're really locked in to such a platform, you no longer have choice and competition and need to accept what your platform offers you. Of course, it's possible to move everything to another provider, but as I've described above, users are lazy and probably won't invest energy into this move unless there's a very strong reason (like apple making iCloud storage 10x more expensive) to do so. So in reality, users are very unlikely to move.

The second problem I see is deletion of data. Nothing's stopping you from accidentally deleting important data. To be fair, most providers have features that let you restore data. This allows data recovery, but the conditions (how long are these backups kept etc.) are mostly unclear and you can also simply delete these backups. If someone's gaining access to your account, they can easily delete your data and the backups. If one of your devices / accounts is infected by a ransomware that threatens to delete your data, a cloud backup likely won't save you. Cloud storages are primarily data synchronization tools and not data backup tools, so good advice is to perform manual backups of the cloud storage. This brings us back to the problems I outlined in the previous section.

## 3. Private NAS

The third option is to buy a NAS, which basically is a large hard drive connected to your network. The advantage compared to cloud storage is that the data is kept on your device and therefore under your control. Modern NAS systems have a lot of features and allow file synchronization across your devices, automated backup and file replication, etc.

I'm using a NAS myself, but I cannot recommend this approach to my non-technical friends and family. Once you operate such a device, you need to constantly invest time to keep it secure (e.g. apply security updates). If you want "advanced" features like being able to access your NAS from the internet, you need to be very carful not to expose your data to literally everyone. Network protocols, port forwarding and knowing what is safe to do is beyond the regular computer user and even experts can easily make configuration mistakes.

Also, if you don't introduce some kind of data backup, your data might still be vunerable to ransomware attacks. A RAID system is not a backup solution!

# Requirements

After looking at these different options and their disadvantages, this is the list of requirements I have for a "really good solution":

- **Data safety**: Data should be kept. Hardware failure should not lead to data loss. Permanent deletion of data should only possible when it's *very* clear that this is the user's intention. The default should be to never permanently delete data.
- **Data security**: The user's data should only be accessible to them and people they've shared it with. 
- **Universal access to data**: The user's data should always be available to them. You can't access all of your 4TB personal data folder on your smartphone when you're not connected to other devices of course, but data should be availalbe as long as that's technically possible.
- **Minimal setup effort**: Setup and configuration effort should be as low as possible. It shouldn't require more than logging into an account or pairing two devices.
- **Minimal maintenance effort**: I initially wanted to write no maintenance effort, but that's simply not possible. Even when using the all-in-one iCloud solution, you still have to accept condition and pricing updates. Nevertheless, the maintenance effort for a user should be as low as possible. Most importantly, there shouldn't be active maintenance required. Getting notified that the hard drive in your NAS needs to be changed is much better than having to actively check once a month.

This list is most likely not exhaustive, feel free to tell me additional requirements you find important.

# Summary

In this post, I described the options I currently see for "regular" people. There's no solution I really like and that I could recommend to everyone. I don't think that it's impossible to have such a solution though. I'm pretty sure it's possible, and probably even much easier than any of the state of the art solutions. I've been thinking a lot about data storage, synchronization and backup lately and believe that great solutions are possible if we do it right. I'll explain my ideas in another post, hopefully soon. For now, here's a short sneak peek of keywords that will be relevant: distributed, p2p, offline-first, hash-based, awesome ;-).