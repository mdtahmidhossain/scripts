# Mounting a Network Drive on macOS

### 1. Create a mount point directory

Open the Terminal app on your Mac and create a directory that will serve as the mount point for the network drive:
```shell
sudo mkdir /Volumes/g_auto
```
### 2. Mount the network drive

Mount the network drive using the following command:
```shell
sudo mount_smbfs //admin:password@network_device/G /Volumes/g_auto
```
Replace **admin** with the network username, **password** with the network password, and **network_device/G** with the network folder address.

### 3. Verify the mount

Verify that the network drive was successfully mounted by checking the contents of the mount point directory:
```shell
ls /Volumes/g_auto
```
If everything was set up correctly, you should see the contents of the network folder displayed in the output of the **ls** command.

# 4. Automatically mount the network drive on startup

To mount the network drive automatically each time your Mac starts up, you can create a script and add it as a startup item.
### 4.1 Create a script

Create a new script file with the following contents:

```shell
#!/bin/sh
sudo mount_smbfs //admin:password@network_device/G /Volumes/g_auto

```

Replace **admin** with the network username, **password** with the network password, and **network_device/G** with the network folder address.

Save the script file to your home directory, for example, as **mount_g_auto.sh**.

Make the script file executable by running the following command in Terminal:

```shell
chmod +x ~/mount_g_auto.sh

```

### 4.2 Add the script as a startup item

Go to System Preferences > Users & Groups > Login Items.

Click the "+" button at the bottom of the list to add a new login item.

Select the script file you created, **mount_g_auto.sh**, from the file dialog that appears and click the "Add" button.

Restart your Mac to see if the script is run on startup and the network drive is mounted automatically.

Note that you may be prompted for your administrator password when you add the script as a login item. This is because the **mount_smbfs** command requires administrator privileges to run.
