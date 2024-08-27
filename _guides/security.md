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