---
layout: post
comments: true
published: true
title: Spinrite on MacOS Using Wine and VirtualBox
---

I tried an experiement out today to see if it was possible to get [Spinrite](https://www.grc.com) running on my Mac. Surprisingly, I was able to do it. If you want to give it a try, this article will walk you through it. Click on each link below to head to that section.

**Prerequisite:** You need to be familiar with using the terminal program on your Mac. As an owner of Spinrite, I'm presuming that you are.

<!--more-->

* [Homebrew](#homebrew)
* [Wine](#wine)
* [VirtualBox](#virtualbox)

# Homebrew

Homebrew is a simple package manager, meaning it's a program that can install other programs to your computer. In the command line world, what you are installing can be dependent on having other things installed to your system. Homebrew knows all this and takes care of magically installing it all for you.

You can get homebrew installed by pasting the following command onto your terminal line and pressing enter:

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

After Homebrew is installed, you should probably run `brew doctor` and resolve any issues it brings up. One example is that you may not have the XCode command line tools installed. This will prompt you to install them.

If you already have homebrew installed, you'll want to run `brew update` before you continue on.

# Wine

Wine is a program that allows you to run Windows programs on your Mac without needing to install Windows. In order to get things installed, we'll use homebrew to do it.

This may take a while, as it will install a number of helper programs for Wine and it may compile some of them for your system. However, it's a simple task, run: `brew install wine` and enjoy watching your computer do all the hard work.

Once installed, you will want to run Spinrite from the directory where it is located. For example, the desktop. To do this, run `wine ~/Desktop/spinrite.exe`, replacing the path to your own copy.

Spinrite should start up. What you want to do now is to create an ISO file of Spinrite. We'll use this later to boot up our virutal machine. Click the button labelled **Create ISO or IMG** and then click **Save a Boot Image File**. You can place this file anywhere you want. Once done, click the **Close** button and exit SpinRite.

# VirtualBox

VirtualBox is a program that allows you to run virtual machines on your Mac. It's similar to Parallels or VMWare with the one exception that it's free. You can install it quickly by running `brew cask install virtualbox`. (Note that cask is an extension program to Homebrew that allows you to install MacOS applications.)

After installing virtualbox, it's time to start it up. You'll find it in your Applications folder.

Once started, create a new virtual machine and give it a name. Then, for the type dropdown, pick other, and ensure the version dropdown shows as DOS. Click the continue button. In the memory size, accept the default and click continue. On the hard disk screen, select **Do not add a virtual hard disk** and click create. The program will yell at you - just click continue.

Next - pick your new virtual machine and click on the settings button. In the storage tab, click on the IDE controller and click the button to add an optical disk. CLick choose disk and pick your SpinRite.iso file as the disk. Then click **OK** to save all your changes.

The last thing is to mount a hard disk for SpinRite to look at. In this case, it will be a USB drive. Make sure that you have your USB drive plugged in and mounted to your Mac. Go back to terminal and type `mount` to see the list of disks mounted on your system. At the bottom of the mount report should be your USB disk - it should show something like `/dev/disk2s1` or `/dev/disk2s2`. Make sure to remember this as we will use it later.

Next, start up **Disk Utility** and go to the name of your drive - this is the child item underneath the actual disk itself. Right-click on it and select **Unmount**.

Finally, it's time to go and create a virtual hard disk to use in your virtualbox. Going back to terminal, type the following command:

    sudo VBoxManage internalcommands createrawvmdk -filename ~/Desktop/usb.vmdk -rawdisk /dev/disk2s2

Of course, make sure to replace the filename with what you want and the proper disk path that you found above.

You now need to set permissions properly on your disk and virtual drive so that VirtualBox can access it. You can do that with the following commands (i'm using the paths from the previous command - make sure to use your own;

    sudo chmod 777 ~/Desktop/usb.vmdk
    sudo chmod 777 /dev/disk2s2

After running those commands, you will now be able to link this virtual drive. Go back to VirtualBox and go into the settings for your virtual machine. Go to the storage tab again and click on the IDE controller. This time, click the button to add a new disk and pick **Choose existing disk**. Go and find your virtual disk file you created and click open. Finally, click the **OK** button to save your virtual machine.

# Testing it All Out

You're now ready to test it out. Click on your virtual machine and click the start button to fire it up. You should see the familiar SpinRite logo and there should be only one disk to select. You can now run SpinRite on your USB mounted disk.

Enjoy and let me know if you have any comments or feedback. I'm happy to keep this as a rolling document, updated with more information.