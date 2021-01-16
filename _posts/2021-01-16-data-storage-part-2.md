---
layout: post
title:  "Data Storage for Humans - Part 2: Requirement implications"
date:   2021-01-16 12:45:56 +0200
categories: data storage cloud synchronization backup safety security idea 
---

*This is the second part of my series "Data Storage for Humans". In the [first part]({% post_url 2021-01-09-data-storage-part-1 %}), I analyzed different options regular users have for storing their data and the problems these options have. I then concluded by providing the following requirements for a "really good solution". In this second part, I want to take a look at how these requirements affect possible solutions.*

## Requirements

For reference, this is the list of requirements I collected in [part 1]({% post_url 2021-01-09-data-storage-part-1 %}):

- **Data safety**: Data should be kept. Hardware failure should not lead to data loss. Permanent deletion of data should only possible when it's *very* clear that this is the user's intention. The default should be to never permanently delete data.
- **Data security**: The user's data should only be accessible to them and people they've shared it with. 
- **Universal access to data**: The user's data should always be available to them. You can't access all of your 4TB personal data folder on your smartphone when you're not connected to other devices of course, but data should be available as long as that's technically possible.
- **Minimal setup effort**: Setup and configuration effort should be as low as possible. It shouldn't require more than logging into an account or pairing two devices.
- **Minimal maintenance effort**: I initially wanted to write no maintenance effort, but that's simply not possible. Even when using the all-in-one iCloud solution, you still have to accept condition and pricing updates. Nevertheless, the maintenance effort for a user should be as low as possible. Most importantly, there shouldn't be active maintenance required. Getting notified that the hard drive in your NAS needs to be changed is much better than having to actively check once a month.

## Implications

So what do these requirements mean for a solution?

First of all, let's talk about *data safety*. Hardware can (and does) fail, so safe data storage requires storing the same data on multiple devices. If one device storing the data fails, there's still another copy available this way. Up-to-date backups on external hard drives are the traditional way to maintain a second copy of your data, but I've already written about the problems with that approach. Manually connecting a hard drive to create backups doesn't work for most people and goes against the requirement of *minimal maintenance effort*. 

The alternative is to use devices that are connected to each other via network. NAS systems are specialized devices for this, but let me remind you that I'm designing for regular (non-tech) people. They won't be able to maintain a NAS system, and I'd argue they needn't. The amount of data most users possess isn't that large. E-Mails, documents and photos rarely add up to a size that really requires large backup hard drives or NAS systems. Let's keep it simple and work with the devices regular users have already (smartphones, laptops, desktop computers, tablets, etc.). Having copies of your photos on your smartphone and your tablet isn't the safest way to prevent data loss, but it's way better than nothing. If users really need more storage space, they could still invest in additional networked storage devices. These could by anything ranging from a hard drive connected to a Raspberry Pi to a full-fledged NAS system. For getting started or simple use cases, this shouldn't be required though.

> - Data needs to be stored on multiple devices.
> - Devices should be connected to each other.

Talking about storing data on multiple personal devices directly brings us to the next requirement: *Universal access to data*. For most users, it wouldn't be practical to store all of their data on all of their devices. Some devices (e.g. your smartwatch) might simply not have enough storage capacity to hold it, and that's ok. *Data safety* is satisfied if the data is stored on (at least) two other devices and as long as your device is connected to one of those other devices, the data can still be accessed. If the device you're using is connected to all of your other devices, you would have access to all of your data, even if it's not stored locally.

But what happens if you're not connected? Many distributed storage systems are centralized, which means that there's a central server holding all data. If you're connected to that server, everything's fine and if not, well, your out of luck. Take Dropbox as an example. You can have multiple devices sharing a folder, but the synchronization is done through a central server. When my internet provider had issues a couple of weeks ago, I couldn't use Dropbox to synchronize files between my laptop and my smartphone anymore, even though they were still directly connected through the local network. This goes against the *universal access to data* requirement. Instead of relying on a central server, devices should be able to work with all other devices they can currently (directly) connect to.

> - Communication between devices should be peer-to-peer (p2p).

When talking about *data safety* before, I didn't talk about deletion of data. Besides hardware failure, data loss can also happen due to unintentional deletion of data. In current file systems, it's pretty easy to accidentally permanently delete data (Shift+Del -> Enter; overwriting an existing file) and many users have their scars from it. There's also malware encrypting your data, thereby deleting the original. 

To satisfy the *data safety* requirement, the system should only permanently delete data if it can be very sure this is intentional. When I say "permanent deletion" here, I mean that there's no way to bring the data back. In comparison, there's also deletion that can be reversed. For example, if a file is stored on two of my devices and I delete it on one of them, it's still available. Another example is something like git where you can delete a file but still get it back by going back to an older version. These are examples of deletion that can be reversed and therefore aren't critical operations. On the other hand, deleting the last copy of a file is permanent and should need additional confirmation. This confirmation could be implemented similar to two-factor authorization. If I want to permanently delete some data, I need to confirm that operation using a second device of mine.

> - Permanent deletion should require additional confirmation.

Another requirement is *minimal setup effort*. Many data storage systems require either manual setup (IPs, ports) and/or password-based authentication to connect devices to each other. Passwords don't really work for humans. Safe passwords are hard to remember and with the number of passwords a user is required to remember steadily increasing, it's more likely that the same passwords are reused. I also think that passwords aren't really necessary here. For example, if you want to use WhatsApp from your laptop, you don't need a password at all. You simply scan a QR-Code and that's it. Pairing bluetooth devices is another example that doesn't require passwords.

The system should not require users to remember passwords. Connecting devices could be done using QR-Codes or simple one-time codes. As there wouldn't be a central service, you wouldn't need to create an account or something like that. Setting up two devices to share data or adding another device into an existing group could be as simple as scanning a QR-Code.

> - Users shouldn't be required to set and remember passwords.
> - Connecting devices should be as easy as possible.

For ensuring *data security*, there are a couple of requirements. First of all, devices should only communicate with devices they have been paired with and this communication needs to be encrypted. Additionally, it's also important that the devices themselves are secure. This includes user authorization (lock screen passcode etc.) as well as storage encryption. These are important topics, but I'd consider them to be beyond the scope of what I'm proposing. Think of the system I'm proposing as an app on your device which builds on the security / authorization model of the platform. That's not ideal, but also the most practical approach. A future extension could be to include user authorization and storage encryption in the system, but I believe that it's ok to leverage prior art here for now. This allows focussing on the core innovations I'm proposing.

> - Communication should only be done between paired devices and needs to be encrypted.
> - Relying on devices for user authorization and storage protection is ok for now.

## Summary

In this post, I have tried to explain how the requirements identified earlier affect a possible solution. I've already had a concept in mind, so writing this blog post sometimes felt like working backwards. I still hope that you could follow the arguments. In summary, here are the main takeaways again:

> - Data needs to be stored on multiple devices.
> - Devices should be connected to each other.
> - Communication between devices should be peer-to-peer (p2p).
> - Permanent deletion should require additional confirmation.
> - Users shouldn't be required to set and remember passwords.
> - Connecting devices should be as easy as possible.
> - Communication should only be done between paired devices and needs to be encrypted.
> - Relying on devices for user authorization and storage protection is ok for now.

## Outlook

There's much more to think and write about. One large topic would be data organization (read "file systems"), another one would be distributed coordination (what to store where etc.). Investigating sharing data with friends and implications of this (data safety, availability, etc.) would be really interesting too. I would also like to present some kind of product vision showing how using the system would look like from a user's perspective. Showing the concept I have in mind currently would also be a good idea. And then there's also the more technical topics: which technology to use, implementing an actual prototype, etc.

I'm not sure what I'll be doing next, but, *hey!*, it's my spare time project and I'm free to do whatever I want whenever I want to. Let's see where this goes. 

If you have feedback, questions or additional information I should look at, feel free to contact me directly, on twitter or join the [discussion](https://futureofcoding.slack.com/archives/C5T9GPWFL/p1610799148017200) in the [future of coding community](https://futureofcoding.org/). Till' next time!
