# ownCloud Desktop and Mobile Client

ownCloud provides a secure and compliant file sharing and synchronization solution on the servers that users can control. Users can share more than one file and folders on their computer, and synchronize the files with their ownCloud server using the ownCloud Desktop and Mobile client.

## ownCloud Desktop Client

A user can download ownCloud Desktop Client from the [ownCloud Download Page](https://owncloud.com/download/#desktop-clients). The Desktop client is available for Windows, macOS, and Linux.

### Installing the ownCloud Desktop Client

This section describes the installation for **Windows**, which is same as for any other software application. However, **Linux** users must follow the instructions provided on the [ownCloud Download Page](https://owncloud.com/download/#desktop-clients), which helps in adding an appropriate repository for their Linux distribution, installing the signing key and accessing the package managers to install the desktop client.

#### System Requirements

- Windows 7+
- Mac OS X 10.7+ (64-bit only)
- CentOS 6 & 7 (64-bit only)
- Debian 8.0 & 9.0
- Fedora 25 & 26 & 27
- Ubuntu 16.04 & 17.04 & 17.10
- openSUSE Leap 42.2 & 42.3

#### Installation

After meeting the above system requirements, perform the following steps to install the desktop client:

1. Run following command to install the client.

  ```
  msiexec /passive /i ownCloud-x.y.z.msi ADDDEFAULT=Client
  ```

2. Pass the LAUNCH property to launch the client automatically after installation.

  ```
  msiexec /i ownCloud-x.y.z.msi LAUNCH="1"
  ```

  **NOTE:** This option does not have any effect without GUI.

##### Installation Wizard

The installation wizard enables the user to perform the configuration and account setup process. When the installation wizard launches:

1. Enter the URL of ownCloud server, click **Next**.

  ![client-install1](/images/2019/08/client-1.png)

2. Enter the ownCloud credentials, click **Next**.

  ![client Installation](/images/2019/08/client-2.png)

3. Sync all the files on the ownCloud server or select individual folders.

  **TIP:** The user can also change the local folder, which displays ownCloud as a default value.

  ![Client Installation Sync](/images/2019/08/client-3.png)

4. Click **Connect**.

  The client connects to the ownCloud server and displays two buttons to:

  - Connect to the ownCloud web GUI.
  - Open the local folder.

  Also, it starts synchronizing the files.

For more information about Desktop Client, please refer [Desktop Client Manual](https://doc.owncloud.com/desktop/2.5/).

## ownCloud Mobile Client

The ownCloud mobile client provides a simplified interface to the users to synchronize and share the files with other ownCloud users and groups.

### Installing Android App

The user can install the ownCloud Android app by logging to the ownCloud server from an Android device using a Web Browser such as Chrome or Firefox.

A screen with the download link appears, which redirects to the Google Play Store. The download link is also available on user's page in the ownCloud Web interface.

![ownCloud Mobile Client](/images/2019/08/android-1.png)

For more information and source code, please refer the [ownCloud download page](https://owncloud.org/download/#mobile).

To connect to the ownCloud server:

1. Enter the server URL.

2. Enter the ownCloud credentials.

3. Select **Connect**.

![ownCloud Server connect Mobile App](/images/2019/08/android-2.png)

### Installing iOS App

Similar to the Android apps, the user can find the download link for ownCloud iOS app on the user's page in ownCloud server when the user logs in using the Web browser in the iOS app.

After launching the ownCloud iOS app, enter the server URL and login credentials, it connects the user to the Files page.

For more information, refer to the [installation](https://owncloud.org/download/) page.
