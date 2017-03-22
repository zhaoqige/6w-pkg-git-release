LICENSE
-------
MIT License

FIRST-TIME USE
--------------
Please DO FORK this repository to your own GitHub account.
And then send "pull request" to update your release. 
If you want to be a collaborator, let me know.

CONDITIONS
----------
Let's say your "build root" is "/openwrt", "archive" is "ar71xx".
Demo package is "grid-lite".

STEPS for CROSS-COMPILING
-------------------------
1. Clean last downloaded file in "/openwrt/dl/grid-lite*";
2. Replace Makefile with this "./lts/";
3. "cd /openwrt; make menuconfig", select this package;
4.1 re-build "cd /openwrt; make";
4.2 or other purpose, try "cd /openwrt; make package/grid-lite/compile", 
and upload "/openwrt/bin/ar71xx/packages/grid-lite_*_ar71xx.ipk" to debug.

SUPPORT
-------
Send email to admin@6wilink.com/qige@6harmonics.com.

GITHUB
------
https://github.com/6wilink/pkg-git-release.git

MAINTAINER
----------
Qige Zhao <qige@6harmonics.com>
