
## 🛠️ Pre-Domain Joining Setup

1. **Configure Network Settings:**
- **Note:** Ensure that you have the correct IP configurations provided by your IT administrator before proceeding.
   - Navigate to **Network & Internet settings**.
   - Go to **Properties** for your network connection.
   - Select **Internet Protocol Version 4 (TCP/IPv4)**.
   - Click on **Properties** and manually configure the following:
     - **IP Address**
     - **Subnet Mask**
     - **Default Gateway**: After entering the default gateway, click on **Advanced**.
     - **DNS Settings**: Add the four IP addresses for DNS.
   - **Warning:** Incorrect IP configuration can cause network connectivity issues. Double-check all entries before proceeding.

## 🏢 Joining the Domain

1. **Join the Workstation to the Domain:**
   - **Important:** Make sure you have your domain user credentials ready for the next login.
   - Log in using your domain user credentials.
   - **Note:** If the domain join fails, ensure that the network settings are correct and that the workstation has network access to the domain controller.

## 🔧 Post-Domain Joining Setup

1. **Enable Windows Features:**
   - Navigate to **Apps & features**.
   - Click on **Turn Windows features on or off**.
   - Look for **MSMQ Server** and check all the options under it.
   - Apply changes and restart the workstation if prompted.
   - **Warning:** Missing features can cause certain applications to fail. Ensure that all required features are enabled.

## 📁 Copying Files from Another Workstation

1. **Copy Necessary Files:**
   - **Important:** Ensure that the files being copied are up to date and relevant to the new workstation's role.
   - Copy the **Camille** folder to the `C:` drive.
   - Copy any necessary **menus** and **airline apps** from the other workstation to the appropriate locations on the new workstation.
   - **Note:** Verify that all copied applications are functioning correctly after the transfer.

## 🔒 Configuring Certificates

1. **Import ZScaler Certificate:**
   - Open **Run** (`Win + R`), type `mmc`, and press Enter to open the Microsoft Management Console.
   - In the console, go to **File** > **Add/Remove Snap-in**.
   - Select **Certificates** and choose **Computer account**, then click **Next** and **Finish**.
   - In the left pane, expand **Certificates** > **Trusted Root Certification Authorities**.
   - Right-click on **Trusted Root Certification Authorities** and select **All Tasks** > **Import**.
   - Click **Next**, browse to `C:\Camille\` and select **ZScaler.crt**.
   - Complete the import by clicking **Next** > **Finish**.
   - **Warning:** An incorrect certificate installation can result in security warnings or connectivity issues. Ensure you select the correct certificate file.

## 🌐 Proxy Configuration

1. **Configure Proxy Settings:**
   - Go to **Settings** > **Network & Internet** > **Proxy**.
   - Under **Manual proxy setup**, add the following address: `185.46.212.90`.
   - **Note:** Ensure that the proxy address is correct and authorized by your network administrator.
   - Open the **Camille** folder and open the `newtextdoc.txt`.
   - Copy the second line from `newtextdoc.txt` and paste it into Microsoft Edge’s address bar.

2. **Run Locator:**
   - Navigate to the **Camille** folder and run the **Locator** file.
   - Go to the `ajflck` folder within the **Camille** folder.
   - Copy the `nodename.lck` file to the **Camille** folder.
   - Update the **ring** and then open the Command Prompt.
   - Navigate to the **Camille** folder and run the `.lck` file.
   - **Warning:** Each workstation has a unique ring number. Ensure the correct ring number is used to avoid configuration errors.

## 🧩 Final Configuration Steps

1. **Install APC Prerequisites:**
   - In the **Camille** folder, click on **APC_Perequasete** and follow the prompts until the installation is complete.
   - Restart the computer when prompted.
   - **Note:** If the installation fails, check that all previous steps have been completed correctly.

2. **Create Necessary Folders:**
   - Navigate to `C:\SITA`.
   - Create a new folder named **Cash** under `C:\SITA\temp`.
   - Create another folder named **LCKFile** under `C:\SITA`.
   - **Note:** Ensure that folder names are spelled correctly to avoid file path errors later on.

3. **Run Services and Installations:**
   - In the **Camille** folder, go to **flexadapterservice** and run the **SITAFlexAdapterService** file.
   - Run **APC_CUTE.msi** from the **Camille** folder.
   - Run **PROD-edgeConfig.reg** to apply the necessary registry settings.
   - **Warning:** Always back up the registry before making changes. Incorrect registry settings can cause system instability.

4. **Configure LCK Utility:**
   - The **LCK Utility Tool GUI** will open.
   - Run **LCKUtilityTools.exe**.
   - In the LCK Utility Tool, select the `nodename.lck` file you copied earlier.
   - Set the **LCK Storage Path** to `C:\SITA\LCKFile` and click **Update**.
   - Restart the computer.
   - **Note:** Double-check the storage path to ensure that all files are correctly saved and accessible.

