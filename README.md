# 2Boots_2560

This is an AVR bootloader mainly inspired from  Thseiler's [2Boots](https://github.com/thseiler/embedded/tree/master/avr/2boots) on GitHub. Like many other people, I've tested and found that bootloader to be working with Arduino Uno (Atmega 328) but didn't have any success with Arduino Mega. Since my current projects needed to be run on Mega, so I took some code from 2Boots and wrote my own bootloader.

# MUST READ!!!

Since It's just a modification of another rep, installation and usage is identical. So, kindly get back on the original article for help before wondering why your arduino is cathich fire. (the later part was a joke). Only the Make part is different but that matters only if you want to experience the pleasure of customizing an exisiting code.

# What's the big deal?

Short story, as discussed on the original 2Boots rep, field programablity becomes easy with an SD card based boot loader.

Long story (for those like me who aren't sharp enough to get the idea in a single sentence, we know that a our favourite Arduino's are usually awesum as long as we are doing DIY fun projects. Changing, and uploading the code works in seconds throught the USB cable. Lets think more practically for a moment. Imagine that we build a commerical dust sampler for some environment scientist, hobbyist or something, living somewhere deep in the mountains, or far in a dessert, observing absolute solitude in quest to find something momentus in the wild. He doesn't like to be messed up in complex things as arduino's and wires etc, so everytime, he requires a software update we will need to travel all the way to him. This is not an issue as long as they are paying good money, but why take so much pain for something so samll! Here comes 2boots, (thanks to thseiler) to rescue us. We modify the bootloader of our arduino only once and whenever it we need an update, the arduino can self update from a file we have copied on the SD card. So this is a big deal...

# What was wrong with the original 2Boots

The original 2boots used an STK500 Version 1 based bootloader for the the Serial/USB uploading. I figured out that some Arduino Mega's (at least, all the lots that I have) are shipped with a robust version of STK500, the Version 2!! All I've done is re-wrote the original main function and included STK500V2 from the original arduino sources. For most parts, we didn't even need the robustness of V2 (occupying  almost 2KWords on the bootloader section). I haven't omitted it, but have put it under an inactive #ifdef. This leaves more space on the bootloader for more intereseting stuff (Like TFT display during the upload!)

# Who can benefit?

For everyone who wishes to run 2boots on any AVR other than 1280 or 2560, (Arduino Mega), kindly view the original 2Boots 
[HERE](https://github.com/thseiler/embedded/tree/master/avr/2boots). All the unlucy people who couldn't benefit from this great effort, and couldn't get it working on the MEGA, dont't worry. Burn the 2boots.hex from this rep using "Arduino as ISP" or other ISP programmer etc. For the rest of the part, Use the instructions from the original rep.

# How to Make

Unlike the original 2Boots, I've moved the code to Atmel Studio 7 with an auto generated Makefile. ALl you have to do is, oepn the project in  Atmel Studio and build it.
