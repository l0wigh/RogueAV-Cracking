# Internet Security 2012

## Pre-Execution Informations

The binary is 32bit application that seems to be packed with a custom packer. It contains some funny sections names. Maybe the dev wanted to talk to the reverse enginners ?

// PEiD screenshot

The binary icon is something related to AMD K6-III CPUs. Was it a fake driver update ?

// Screenshot of the icon

Let's launch it !

## Post-Execution Informations

First the binary install and launch the FakeAV called Internet Security 2012. Then it remove itself, leaving a "nicely" made AV running a scan and finding threats on a newly installed Windows 7 machine.

Ok, let's launch a debugger and cr... Wait ? It closes the application ? Same thing with WinRAR, Firefox and even the Calculator ?

// Screenshot of the message

Obviously after a reboot, the FakeAV take back the control and block everything again. I also can't remove the binary, or block it's autostart by launching msconfig.

## Debugging and Cracking

Let's stop this infection for good by using the darkest, deepest, most secret tech : renaming my debugger. Yep you guess it, it just verifies if the name of the binary that want to start is called "isecurity". Nothing too crazy right ?

// x64dbg_launched.png

We are now attached and ready to stop the infection by cracking the FakeAV. Let's do the simple "return to user" trick. First, I open the Activation Window

// activation_window.png

I enter random stuff in the boxes and click "Confirm Activation". A popup opens. Now let's pause the process inside x32dbg and click on the button "return to user" and close the error window. The debugger stop the execution and we are just after the message box. Well, seems like the debugger found an interesting key !

// Key screenshot

After changing the email, it's seems like a unique key that unlock the malware. Well not a really secure way to protect your prescious app...

You just need to have a valid email. I mean, having an @ inside the email input box.

// registered.png
// registered2.png

## What we learned

This one was not that hard to understand and crack. The simple bypass of the binary name security was really easy, and the key was in front of us with the good breakpoint. 