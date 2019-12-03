# BFFx64
CERT's Basic Fuzzing Framework, but 64 bit. 

Yet to be done - all code except that created by the fine people at CERT is LGPL3.
This is probably gonna be pretty janky - will put together when I wake up.


### Why?

Due to the limitations of the 32 bit architecture of the packages distributed with the original CERT-BFF, it will encounter a MemoryError pre-emprively before approaching 2-3 GB of RAM usage. This hacky workaround was made to fix this issue that, while a small amount may only encounter, is quite a pain in the ass.

#### Installation (Windows)

Clone the repository, then install CERT-BFF as normal. Of note - remove all exisiting Python installations beforehand, this is best done on a clean machine (spare drive, pocket SSD, what-have-you). 

After the installation has finished, go to the control panel and remove everything installed, including the Python modules and Python distribution itself. **Do not remove anything in C:\BFF, or the debugging tools for Windows, MSEC, or anything else non-Python**. Next, you'll want to install Python 2.7.12 x64. It's ancient, it sucks, but it's what BFF apparently needs, and I'm too lazy to write anything better or refactor the code. **Make sure you include Python in your PATH variable!**

From then, you'll want to use `pip` to install the wheel packages in the *REQUIRED* folder. You'll want to start off with NumPy, and then SciPy, for some errata that I'm not fully aware of. Feel to free to install the rest in whatever order you prefer, but I usually do PyYAML -> pywin32 -> WMI. But you're not done yet. Open up an **Administrator** command prompt or alternative of your choosing and chdir to Python27 (where your new, fancy x64 2.7.12 install should be). Then execute the following.

`python(.exe)Scripts/pywin32_postinstall.py -install`

#### Installation (Unix and Unix-likes, macOS, Linux, *BSD)

Why are you even here?

#### Greetz; Attribution; whatever you call it.

All modules were downloaded from [here](https://www.lfd.uci.edu/~gohlke/pythonlibs), and the Python 2.7.12 x64 distribution was taken straight from [here](https://www.python.org/downloads/release/python-2712/). If you don't trust the modules or installer provided by me, then by all means, download them yourself! Have fun with BFF without a shit memory limit!

#### Errata
I highly reccomend doing this on a virtual machine (KVM or something similarly high-performance, Parallels for macOS could work too) or on a spare drive that you can install Windows on just for fuzzing. This Python distribution, as far as I know, is not compatible with Immunity Debugger, which, despite old, is still a valuable tool. I may or may not create a tool to automate this; and **it is to note that the `LICENSE` file applies to none of the files distributed (aside from README.md?) unless I create something to automate this.**

# Happy Fuzzing!
