# Windows not booting because of missing files

Problem: Files from boot partition of windows are missing and need fixing. This mostly applies for UEFI systems as for BIOS there is probably a better solution.

## How to fix it?

1. Boot into windows recovery screen \(it should get you in here if auto repair failed multiple times\)
2. Select more options
3. Select command line
4. In command line type `diskpart` \(this will be our tool for mounting the partitions\)
5. When you're in diskpart command line, find your windows partition where C: drive would normally be. You do this by typing `list volume` you also need to remember where your boot drive is. Usually it's X: but it might change
6. Select that partition using `select volume <your number here>`
7. Now assign the letter, I fill use N: for this example, using `assign N:`
8. You should now assigned the letter, to exit diskpart use `exit` command or click ctrl+c
9. **Now for the fixing process:**
10. In command line type `bcdboot <drive where C: normally is, in this example it was N>:\windows /s <your boot drive, usually X>:` Example command: `bcdboot N:\windows /s M:`
11. After some time you should be fine, you can restart the machine and test if your operation was successful :\)

## Additional notes:

[Documentation for diskpart if you're unfamiliar with it or have a difficult time reading the help from cmd ](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/diskpart)

From what I remember for BIOS there was bootrec, you can try researching it on your own if this method didn't work



