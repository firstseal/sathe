---
title: The Ultimate Security Guide
description: A guide on how to be secure, and stay secure on the internet.
layout: guide_post
toc: true
---

> The information provided is "as-is" and comes with no guarantee.
{: .prompt-warning }

This guide is focused strictly on *security*.

## Hardware

Securing the hardware we are using is the most critical thing within OPSEC. If the hardware is compromised, it is assumed everything done on that device is compromised as well. There is no point in security if you cannot be *reasonably secure* on the device you are using.

*reasonably secure* meaning that you can safely *assume* security on your device. For instance, a fresh-install of Windows, Linux, etc. without verifying the install. It can be *assumed* to be secure, but ultimately within secure systems, it is imperative to verify the integrity of the OS before we even begin.

In the modern age, it is extremely difficult to have a system that is 100% secure. Can you trust your CPU? Who's to say that a state actor or a malicious employee didn't implant malicious micro-code at the factory level? Can you trust the device and all of it's components? Do you *trust*? Everything comes down to *trust*. At what point can you trust something and not trust it? Ideally, you would verify everything from the code in the linux kernel, to the firmware that runs your HID's. Reviewing all of this code by yourself is a daunting task that very few accomplish. At some point, you *will* have to trust something. Whether it's the word from the community that something is "secure" or that there *isn't* a backdoor in your CPU.

<div style='text-align: right;'>
    <h3>Storage</h3>
</div>

In terms of secure storage, the debate ultimately arrives at HDD vs SSD. The main difference in terms of security for HHD's over SSD's is that with HDD's you can visibly inspect the platter for writed content. HHD's physically write 1's and 0's onto the platter with a small magnetic needle. Since the platter is essentially a physical "CD" we can clearly inspect it. When utilizing secure deletion, it is paramount to verify that the content has actually been overwritten. With HDD's you can verify this. With SSD's you cannot.

<div style='text-align: right;'>
    <h3>Additional Readings</h3>
</div>

- [Supply Chain Security](https://en.wikipedia.org/wiki/Supply_chain_security)\

## Operating System

In terms of security, the *best* operating system is going to be [Qubes OS](https://www.qubes-os.org/). QubesOS is based upon virtualization which provides the best security we can achieve on a personal system. Of course, it is absolutely crucial to [verify the signature](https://www.qubes-os.org/security/verifying-signatures/). If the image is malicious, then it can be assumed the entire device is infected as well.

Qubes is comprised of several "virtual systems" (technically they are *not*, but for terms of those who are not famillear with Qubes) called Qubes. Each of these are based upon their own templates. What seperates Qubes from using several VMs on a host, is the base image is provided as a template. Each Qube will utilize the selected template, the OS files in the Qube are volitile meaning that if you need to make changes to the actual *host* (template), you can do so in the template Qube. Changing a setting in the template will persist to all Qubes with those selected as the template.

With Qubes, you can induldge in some extremely crazy things. Each USB device connected can be automatically attached to a ``sys-usb`` Qube, meaning that a potentially malicious USB device is immedietely sandboxed in an offline Qube. On top of that, it is possible to have private keys stored in an offline Qube, and use passthrough to sign and verify signatures to a Qube connected to the network, all while keeping your private keys offline & secure within their own Qube.

The possibilities are quite infinite with Qubes. Discussing them all here is impractical for the scope of this guide.