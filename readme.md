Running Far Cry 1 with Cheats Enabled on Linux (Wine)

This guide provides instructions for running Far Cry 1 with cheats enabled on Linux using Wine. Far Cry 1 is a classic first-person shooter game developed by Crytek.
Prerequisites

    * Wine installed on your Linux system
    * Far Cry 1 installed in your Wine environment
    * Basic knowledge of using the terminal

Steps
1. Verify Installation Directory

Ensure that Far Cry 1 is installed in the correct directory within your Wine environment.
for example

```
ls "/home/zdislav/.wine/drive_c/GOG Games/Far Cry/Bin32/"
```

2. Correct Path in the Script

Update the launch script (start_farcry.sh) to point to the correct directory.

``nvim ~/start_farcry.sh``

Ensure that the script contains the correct path:
```
#!/bin/bash
export WINEPREFIX="/home/zdislav/.wine"
cd "/home/zdislav/.wine/drive_c/GOG Games/Far Cry/Bin32/"
wine FarCry.exe -DEVMODE
```
3. Make the Script Executable
```
chmod +x ~/start_farcry.sh
```

5. Troubleshooting Errors

If you encounter any errors during the process, here are potential solutions:

c0000135 Error: This error indicates missing or improperly installed components. Reinstall DirectX and Visual C++ libraries using winetricks.
```
winetricks d3dx9 vcrun6
```
File Not Found Error: Ensure that the path in the script is correct and the executable (FarCry.exe) exists in the specified directory.

Application Could Not Be Started: This error may occur due to various reasons, such as incorrect file associations or missing DLL files. Check Wine configuration, reinstall Wine, and verify file permissions.

ShellExecuteEx Failed Error: This error often indicates a file not found or permissions issue. Double-check the path and file permissions.

Additional Notes

    Debugging: Run Wine in debug mode (WINEDEBUG=+loaddll) to get more detailed error messages.

    Permissions: Ensure that all files in the Wine prefix are owned by your user account.

    Dependencies: Install necessary libraries using winetricks to meet dependencies.





