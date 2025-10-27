# 🧪 Experiment 6: Use Sleuth Kit to Analyze Digital Evidence

## 🎯 Aim
To analyze a digital forensic image using **The Sleuth Kit (TSK)** on Kali Linux and extract detailed information about partitions, file systems, and metadata from the evidence image file (`Dell.E01`).

---

## 🧠 Description
**The Sleuth Kit (TSK)** is an open-source digital forensics toolkit that allows investigators to examine disk images and recover evidence.  
It provides command-line utilities for analyzing file systems, partitions, deleted files, and more.  

In this experiment, we used various Sleuth Kit tools — including `img_stat`, `mmls`, `fsstat`, and `mmcat` — to investigate the disk image `Dell.E01`, a forensic image in **EWF format (Expert Witness Format)**.

---

## 🧰 Tools Used
- **Operating System:** Kali Linux  
- **Forensics Tool:** The Sleuth Kit (TSK)  
- **Evidence File:** Dell.E01  
- **Commands Used:** `stat`, `img_stat`, `mmls`, `fsstat`, `mmcat`  

---

## ⚙️ Commands Used and Observations

### 1️⃣ Check File Metadata
```bash
stat Dell.E01
```
![alt text](<Output Screenshot/Exp6/WhatsApp Image 2025-10-28 at 01.18.46_3d8b2e2f.jpg>)
This command verifies that the image file is accessible and provides timestamp details for the investigation.

---

### 2️⃣ Identify Image Type and Size
```bash
img_stat Dell.E01
```
![alt text](<Output Screenshot/Exp6/WhatsApp Image 2025-10-28 at 01.18.46_7b6d7b34 copy.jpg>)
This confirms that the image is in **EWF format** and provides total data size and sector size.

---

### 3️⃣ View Partition Layout
```bash
mmls Dell.E01
```
![alt text](<Output Screenshot/Exp6/WhatsApp Image 2025-10-28 at 01.18.46_7b6d7b34.jpg>)
The **`mmls`** command reveals that the image contains an **NTFS/exFAT partition**, along with unallocated space.  
This helps determine where file system analysis should begin.

---

### 4️⃣ Analyze File System Information
```bash
fsstat -o 2048 Dell.E01
```
![alt text](<Output Screenshot/Exp6/WhatsApp Image 2025-10-28 at 01.18.46_09d9a6ec.jpg>)

In this case, the tool could not identify the file system — likely due to corruption or encryption in the E01 image.  
However, we know from `mmls` that the partition is NTFS/exFAT.

---

### 5️⃣ Attempt to Extract File System Data
```bash
mmcat -i ewf Dell.E01 2 > partition.dd
```
![
](<Output Screenshot/Exp6/WhatsApp Image 2025-10-28 at 01.18.46_78bfe183.jpg>)

When initially executed without the `-i ewf` flag, an error appeared. Adding `-i ewf` specifies the input image type correctly and allows carving the partition into a separate `.dd` file for further examination.

---
![alt text](<Output Screenshot/Exp6/WhatsApp Image 2025-10-28 at 01.18.46_346546fb.jpg>)


## 🏁 Conclusion
The experiment successfully demonstrated how to use **The Sleuth Kit** to analyze digital forensic evidence from an E01 image.  
Key takeaways include:
- Identifying image type and partition layout  
- Understanding sector and volume information  
- Handling forensic errors and EWF-specific commands  

This exercise provides a foundational understanding of digital evidence examination using open-source forensic tools.

---
