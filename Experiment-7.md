# Ex.No.7: Use AFLogical OSE to Extract Data from an Android Device

**Description**

**AFLogical OSE (Open Source Edition)** is a tool used to extract data from Android devices. It’s part of the **Open Source Android Forensics project** and is often used for **logical extraction**, which means pulling data like contacts, messages, and call logs **without directly accessing the file system**. Here’s a step-by-step guide to using AFLogical OSE to extract data from an Android device.

---

## 🚀 Step 1: Prepare Your Environment

* **Download AFLogical OSE:**
    Visit the AFLogical OSE GitHub page and download the latest release. Alternatively, you can clone the repository using Git.
* **Install Java (if not already installed):**
    AFLogical OSE requires Java to run. Make sure you have **Java** installed on your machine. You can download it from the official Java website.
* **Install Android Debug Bridge (ADB):**
    **ADB** is a command-line tool that allows communication with Android devices. Download it from the Android Developer's website and install it on your system.
    * Add **ADB** to your system's **PATH** environment variable to easily run ADB commands from the terminal or command prompt.


![alt text](<Output Screenshot/Exp7/Screenshot 2025-10-28 114758.png>)





* **Enable USB Debugging on the Android Device:**
    1.  On the Android device, go to **Settings > About Phone** and tap **Build Number** seven times to enable **Developer Options**.
    2.  Go to **Settings > Developer Options** and enable **USB Debugging**.
![alt text](<Output Screenshot/Exp7/WhatsApp Image 2025-10-25 at 22.39.06_7ac867cc.jpg>)
---

## 🔌 Step 2: Connect the Android Device to Your Computer

* **Connect via USB:**
    Use a **USB cable** to connect the Android device to your computer.
* **Verify ADB Connection:**
    Open **Command Prompt** (Windows) or **Terminal** (macOS/Linux) and run:

    ```bash
    adb devices
    ```
    This command lists connected devices. If your device is listed, you are ready to proceed. If not, ensure that USB Debugging is enabled and that the correct drivers are installed.

---

## 💾 Step 3: Extract Data Using AFLogical OSE

* **Run AFLogical OSE:**
    Navigate to the directory where you have downloaded or extracted **AFLogical OSE**.
* **Push the APK to the Android Device:**
    Run the following command to install the AFLogical OSE APK on the device:

    ```bash
    adb install aflogical.apk
    ```
    This installs the AFLogical app on the device, which will be used to collect data.
* **Launch the AFLogical OSE App on the Device:**
    On the Android device, open the **AFLogical app**.
    You’ll see options to extract various types of data (e.g., contacts, SMS, MMS, call logs). **Select the data types you want to extract.**
* **Start Data Extraction:**
    Once you’ve selected the data types, the app will start the extraction process.
    Data is stored in **.csv files** on the device’s storage, typically in a directory named `aflogical`.
![alt text](<Output Screenshot/Exp7/WhatsApp Image 2025-10-25 at 22.49.18_32db4995.jpg>)
---

## 📤 Step 4: Transfer Extracted Data to Your Computer

* **Use ADB to Pull Data:**
    After extraction, you need to transfer the data files from the Android device to your computer. Run:

    ```bash
    adb pull /sdcard/aflogical /path/to/destination
    ```
    Replace `/path/to/destination` with the directory path where you want to save the extracted data on your computer.
* **Verify the Data:**
    Navigate to the destination directory and check the **.csv files** to ensure all required data has been extracted.

---

## 🔎 Step 5: Analyze the Extracted Data

* **Open the CSV Files:**
    Use **Excel, Google Sheets, or any text editor** to open and analyze the **.csv files**. These files contain the extracted data like contacts, SMS, MMS, and call logs.
* **Review and Document:**
    Carefully review the data for any relevant information. Document your findings and consider exporting the data into a report format for further analysis.

---
![alt text](<Output Screenshot/Exp7/WhatsApp Image 2025-10-25 at 22.56.41_fb5d92bd.jpg>)
## 🧹 Step 6: Clean Up

* **Uninstall AFLogical OSE:**
    Once data extraction is complete, you can uninstall the AFLogical OSE app from the Android device by running:

    ```bash
    adb uninstall com.viaforensics.android.aflogical
    ```
* **Disconnect the Device:**
    Safely disconnect the Android device from your computer.
    
![alt text](<Output Screenshot/Exp7/WhatsApp Image 2025-10-25 at 23.03.41_be47eb64.jpg>)
# Step 7: Clean Up
----------------
Uninstall the app after completion:  
**Command:**  

# 🔍 Observations
----------------
| File Name     | Contents Description                     |
|---------------|------------------------------------------|
| contacts.csv  | Contact list with names and numbers      |
| sms.csv       | Text messages sent and received          |
| mms.csv       | Multimedia message records               |
| calllog.csv   | Incoming, outgoing, and missed calls     |

# 📈 Result
----------------
Logical extraction was successfully performed using AFLogical OSE.  
Extracted data was saved in .csv format and verified using spreadsheet software.

# 📚 Conclusion
----------------
This experiment demonstrates that AFLogical OSE provides an efficient and non-invasive method to extract important user data from Android devices.  
It is useful for forensic investigations and digital data recovery.