---
description: >-
  Get your bot up and running, a brief guide / link collection for new Gunbot
  users.
---

# Quickstart guide

## 1. Download software

The latest stable version of Gunbot is always available on Github. 

{% page-ref page="download.md" %}

## 2. Install & startup

The installation procedure is pretty straightforward, although there are slight differences between operating systems. 

* Unpack the zip file to a new folder
* On Mac and Linux: set executable permission for the program
* Depending on your firewall: allow TCP traffic on the port used for the interface \(default port: 5000\)
* Start executable file and visit the interface in your browser on: [http://localhost:5000](http://localhost:5000)

| Links to operating system specific install guides |
| :--- |
| [Windows](windows.md) |
| [macOS](macos.md) |
| [Linux](linux.md) |
| [ARM](linux.md) |

{% hint style="info" %}
On Mac systems, expect to have to explicitly allow running various libraries used by Gunbot due to Gatekeeper.
{% endhint %}

## 3. Enter license related data

Before you can start actually trading with the bot, you'll need to enter a few things to make sure it will pass the license checks.

When you first start the interface, it will show a window that guides you through the initial setup of:

* Entering the wallet address where you hold your Gunthy tokens
* Connecting one exchange for which you've registered an API key after your order

![](../../.gitbook/assets/image%20%2860%29.png)

Save the settings after completing the wizard.

{% hint style="info" %}
Pick "other" if your registered exchange is not listed on the setup wizard.   
After saving, you can enter the exchange details on the profile page.
{% endhint %}

