# Smart Fortress 2012

## Pre-Execution Informations

32bit application, in C++ and doesn't seems packed.

// PEiD and Logo icon

Let's infect the ASUS Brick !

## Post-Execution Informations

The binary delete itself but nothing happens.

After a reboot, we are indeed infected.

// Image of the Rogue after reboot

Basic registration form that is asking only a key. Let's crack it !

## Debugging and Cracking

This rogue block all applications to start. Nothing too fancy, just rename the app you need to open with the name of the rogue.

// Image of the EvO_DBG opened

Now let's attach and test if the "return to user" trick. Unfortunately, it doesn't work, we will need something else.

Let's try to watch the call stack.

// Stack picture

Breaking on the last element of the stack doesn't give the good positionning. We will need to go higher. Let's use the "return trick" (Xyl2K <3)

I change the first line of the function to retn and double click it. Then I put a breakpoint on the higher function and revert the change. Finally, I have to hit the breakpoint again.

After the breakpoint reached again, I followed step by step what the function does. Image is better than words, so look at the picture to understand.

// Function picture

## What we learned

Nothing really interesting in this one. Changing the Z flag did the trick and the Rogue is now registered and let me use the computer normally.

The return trick is really usefull when using the call stack doesn't go too deep and the "return to user" trick fail.
