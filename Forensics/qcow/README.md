# QCOW(Cyberstakes 2017 -> HackCenter)
The problem gives us a qcow2 disk image and only says *MOO?* <br />
**The Takeaway**<br />
Good to help understand what disk images are and to get into the basics of foresnics thought process.<br />
**The Hints**<br />
1. What is a qcow?
2. Are there any standard tools for dealing with qcows?
---

So if we follow common procedure for foresnics problems we should first learn what a qcow is and then `strings` it.
A qcow2 disk file is a special formatting for disk images and due to that normal commands like `xxd` and `strings` normally
gives some weird input.<br />

**For Example:**<br />
The output of `strings qcow1.qcow` is:
![string.png]

So what are some standard tools for qcow files? One is qemu(you may have to isntall it)<br />
If we run `qemu-img convert qcow1.qcow test.raw` then we will get a raw image that is is formatted more friendly and now
if you `xxd` or `strings` the file you will get the flag: **qcow_says_qemoo_4BEdDAAD0aDbd2E1a6c01B3eb6A7D8a6**

---
**xxd Output**<br />
![xxd.png]

---
**Strings Output**<br />
![stringraw.png]
<br />
---

*Fun Fact*<br />
I over complicated the problem and didn't follow normal xxd/strings procedure if I had I would've saved a couple hours
