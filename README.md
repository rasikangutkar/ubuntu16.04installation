# ubuntu16.04installation
Installation of Ubuntu 16.04.1 alongside Windows 10 . Specifically for Dell 15 7559 with Nvidia GTX 960M
Errors faced:
1. Infinite splash screen before installing ubunutu
2. Input/Output error 5 while copying files during ubuntu error
3. NMI watchdog error during shutdown
4. No grub menu after updating drivers


Steps taken to install ubuntu on dell 7559 with nvidia gpu

1.Install pen drive linux


2.Download iso of ubuntu 16.04.1


3.Make a partition 60 gb (check this->64410mb)


4.Make the drive in pendrive linux


a.NOTE: I had the iso on an external hard disk. Insert the hard disk and pendrive in USBs with the same speed to avoid error along the lines of: Input output error while copying files Replace hard disk, place in cool area, speed different or too fast  

  
5. Restart laptop and press F12

6. Keep secure boot disabled

7. Keep in UEFI mode

8. Select the pendrive in the UEFI options

a.NOTE: Don’t change the port from which the USB was written to a slower or faster port. Causes the error along the lines:  Input output error while copying files Replace hard disk, place in cool area, speed different or too fast


 9. Highlght TRY ubuntu and press e

 10. After quick splash add acpi=off OR nomodeset I think I did the first one 

 11. Ubuntu desktop starts up 

      10. Click on install ubuntu

      11. Fill in all requirements

      12.  When asked for third party software ALLOW and CHECK TURN OFF SECURE BOOT

      13. Let the installation complete . IF you get any error like input output error check step 4 and step 8. If none work try making the USB with RUFUS instead of pendrive linux.

14. Installation complete and reboot.

15. If it directly goes to UBUNTU without showing the grub screen

16. In ubuntu go to additional drivers I switched it from the noveau to nvidia

17. After this the while rebooting the grub menu disappeared

18. To fix this boot into UBUNTU ( black screen shows up hold down shift key this is supposed to help)

19. Now open the command prompt 

20. Run sudo gedit /etc/default/grub

21. Make sure the HIDDEN are commented and go to the resolution line with vbiedit

22. This line is commented 

23. To find the resolution of your screen open another terminal and run xdpyinfo  | grep dimensions 1920x1080 for me

24. Uncomment the line in the grub file and replace it with the output dimensions

25. Sava and Close

26. Run sudo update-grub

27. Now shutdown and reboot

28. You should have the grub menu present now.

HOPE THIS WORKS
