---
layout: post
title:  "Why Android emulator is so slow? Emulators vs Simulators."
date:   2015-11-05 17:01:00 -0200
categories:
---

In order to develop an Android application you need a Android device or use the emulator. Using real device whenever possible is always indicated, besides being faster it gives to your a real experience.
Unfortunately it not always possible to test on real devices, Inevitably the emulator is necessary. Either to test some specific version of the OS, specific dimensions of the device or to run integration test in the cloud.
Yesterday I wrote about [how to send SMS to the emulator](https://guitcastro.github.io/jekyll/update/2015/11/04/send_sms_android_emulator_en.html), today I am going to explain the differences between an emulator and a simulator and why the Android emulator is so slow.

First we need to understand why the emulator is so slow, who already developed iOS applications knows that applications are executed very smooth in the simulator. 
This is because when you develop iOS applications you use a **simulator** and not an **emulator**.

Emulators mimic the and hardware environments found on actual devices. An ARM android Emulator mimic the ARM instructions as if they would have performed in an ARM CPU, even if the host machine has a x86 architecture.
Beside some instructions are very similar, For an accurate emulation it's (usually) not enough to translate each instruction, it is necessary to handle memory accesses, timing, interrupts... and that's just for the CPU.  
Emulators provide a more accurate experience in exchange of a poor performance. [To emulate a perfect SNES](http://www.tested.com/tech/gaming/2712-why-perfect-hardware-snes-emulation-requires-a-3ghz-cpu/) A 3GHz processor is need, 140 times more powerful than the chip inside the Super Nintendo.

Simulators, on the other hand, only mimic the software environment without concern about the underlay architecture. They, otherwise have access to all of the host system's hardware resources such as disk space, memory and processor speed.
This is why they are so much faster, but this also have a counterpoint. Because the iPhone simulator don't have the same architecture from iOS device, two version of the same application have to be compiled. 
If you are using some third party library it have to be compile for both architectures, to run  the application in the simulator and in the device (fortunately this is true for most of them).
Simulators provide a faster but less accurate experience. The iOS simulator is case sensitive, but the device its not. When trying to display an image from a file the image can be successful loaded on the device, but not on the emulator,
according to the string used for the file name.

Hope you have understand the difference between emulators and simulators, and the advantages and disadvantages of each. In my next post I will write tips for speed up the Android Emulator.

#Referências

http://stackoverflow.com/questions/1584617/simulator-or-emulator-what-is-the-difference  
http://stackoverflow.com/questions/4544588/difference-between-iphone-simulator-and-android-emulator
http://superuser.com/questions/697322/why-cpu-emulation-is-slow