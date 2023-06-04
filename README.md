# Guide: Enabling Remote Drive Sharing on Windows for Network Access
[![Video](https://img.youtube.com/vi/SjYUv1ytscE/0.jpg)](https://www.youtube.com/watch?v=SjYUv1ytscE)

To enable remote sharing and share a drive on your Windows computer, you can follow these steps:

1. Open File Explorer (Windows Key + E).
2. Navigate to the drive you want to share.
3. Right-click on the drive and select "Properties" from the context menu.
4. In the Properties window, go to the "Sharing" tab.
5. Click on the "Advanced Sharing" button.
6. Check the box that says "Share this folder."
7. By default, the share name will be the drive letter (e.g., "C"). You can change the share name if desired.
8. Click on the "Permissions" button.
9. In the Permissions window, you can assign the appropriate permissions for the shared drive. By default, the "Everyone" group has Read access. You can add specific users or groups and customize their access permissions as needed.
10. Click "OK" to save the permissions.
11. Click "OK" to close the Advanced Sharing window.
12. Click "OK" to close the drive's Properties window.

At this point, the drive should be shared on your local network, and other computers on the network should be able to access it.

To access the shared drive from another computer:

1. Open File Explorer on the remote computer.
2. In the address bar, enter the following in the format `\\computer_name\drive_letter`, replacing "computer_name" with the name or IP address of the computer sharing the drive, and "drive_letter" with the letter assigned to the shared drive (e.g., `\\192.168.1.100\C`).
3. Press Enter or click the arrow button next to the address bar.
4. If prompted, enter the credentials of a user account on the computer sharing the drive. This could be the username and password of an account that has access to the shared drive.
5. Once authenticated, you should be able to access the shared drive and its contents from the remote computer.

Remember to exercise caution when sharing drives remotely, as it can potentially expose your files and data to unauthorized access. It is recommended to secure your network and apply appropriate access controls to ensure the privacy and security of your shared resources.

## Accessing the Shared Drive with Administrative Permissions

If you want to access the shared drive with administrative permissions, follow these additional steps:

1. Open the Registry Editor by pressing Windows Key + R, typing `regedit`, and hitting Enter.
2. Navigate to the following registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`.
3. If the `LocalAccountTokenFilterPolicy` entry does not exist, right-click on the "System" key, select "New," and choose "DWORD (32-bit) Value" to create a new entry.
4. Name the new entry `LocalAccountTokenFilterPolicy`.
5. Double-click on the `LocalAccountTokenFilterPolicy` entry and set its value to `1`.
6. Close the Registry Editor.

By following these additional steps, you will be able to access the shared drive with administrative permissions without the need for a password.

Note: Modifying the registry can have significant effects on your system. Proceed with caution and create a backup of your registry before making any changes.
