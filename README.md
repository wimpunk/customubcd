customubcd
==========

Notes and configuration about my personal customisation of ubcd which I use a
replacement of my pendrive stick.  There is a nice [customisation page on the
ubcd website][2] which describes how to do it but I thought it would be handy
to keep my own version available online. You never know when you need it.
There could be a stick-crash onetime.

Installation
============

Get an Ultimate Boot CD image from the [ubcd website][1].  Be a 
little fair and use the torrent version.  It reduces the bandwith usage on the
mirrors and prevents the need of more bandwidth.  If you really have no
torrent possibility, you can use the mirrors.  Don't forget (in both cases) to
check the md5 after downloading.

After downloading the image I extracted the image to my usbstick as instructed
on the website and ran `syslinux -f /dev/sde1` to make the stick bootable.
The instructions can be found on the [customisation page][2]

Customisation
=============

To customize your stick, just copy the configuration files to the directory
`ubcd/custom` on the stick.  Don't forget to add the needed iso images to
stick.  Without the iso images, it really won't work.

Testing
=======

You can test your configuration for example in virtual box.  I've created a dd
of my USB stick called ubcd.img and created a vmdk by running

    VBoxManage internalcommands createrawvmdk -filename ubcd.vmdk \
       -rawdisk ubcd.img

I added this image to a pretty small virtual environment with only enough memory
and the generated vmdk as disk.

If you want to change anything in the image from outside a virtual machine
you can mount it as a loop device on linux or use hdiutil on macosx:

    hdiutil attach ubcd.img



[1]: http://www.ultimatebootcd.com/
[2]: http://www.ultimatebootcd.com/customize.html

<!-- vim: set ai ts=4 sw=4 tw=78 : -->

