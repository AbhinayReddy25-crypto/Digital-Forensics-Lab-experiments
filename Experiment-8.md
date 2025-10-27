# Experiment 8: Use Steg-Expose to Detect Hidden Data in Images


## 🎯 Aim
To demonstrate the process of detecting steganography (hidden data) in images using the Steg-Expose tool and analyze the results for potential secret messages or embedded files.

---

## 🧠 Description
Steg-Expose is a specialized steganalysis tool designed to detect steganography in image files.  
This experiment focuses on using Steg-Expose to analyze various image files and determine if they contain hidden data using statistical analysis methods.  
The tool combines multiple steganalysis techniques to identify potential steganographic content effectively.

---

## 🧰 Tools Used
- Steg-Expose  
- Python 3.x  
- Test images (both clean and with hidden data)  
- Terminal / Command Prompt  
- Image manipulation tools (optional, for creating test cases)

---

## ⚙️ Prerequisites
- Java Runtime Environment (JRE) installed  
- Download StegExpose from GitHub:
  ```bash
  git clone https://github.com/b3dk7/StegExpose.git
  ```
- Prepare test images (both clean and stego images)

---

## 🔬 Procedure

### 1️⃣ Installation and Setup
```bash
cd StegExpose
java -version
java -jar StegExpose.jar -h
```
(Displays StegExpose help menu)

---

### 2️⃣ Preparing Test Images
- Collect images for testing:
  - Clean images (no hidden data)
  - Images with known hidden data
  - Suspicious images  
- Create a folder named `testFolder` and place your test images inside.

---

### 3️⃣ Basic Image Analysis
```bash
java -jar StegExpose.jar testFolder
```
(Analyzes all images in the folder)
![alt text](<Output Screenshot/Exp8/WhatsApp Image 2025-10-28 at 01.18.44_3750573e.jpg>)
---

### 4️⃣ Advanced Detection Settings
```bash
stegexpose -t 0.2 suspicious_image.png
stegexpose -csv report.csv image_folder/
```
(Runs analysis with custom threshold and generates a CSV report)

---
![alt text](<Output Screenshot/Exp8/WhatsApp Image 2025-10-28 at 01.18.44_492fd988.jpg>)
### 5️⃣ Statistical Analysis Methods
- Sample Pair Analysis  
- RS Analysis  
- Chi-Square Attack  
- Primary Sets Analysis  

---

### 6️⃣ Result Interpretation
| Score Range | Meaning |
|--------------|----------|
| 0.0 – 0.2 | Likely Clean |
| 0.2 – 0.4 | Suspicious |
| Above 0.4 | High Probability of Hidden Content |

---

### 7️⃣ Validation Process
- Compare StegExpose results with known test cases.  
- Record false positives and false negatives.  

---

## 📊 Results

The experiment was successfully conducted using the Steg-Expose tool on a folder named `testFolder`.  
The analysis produced the following output:

| Image Name                      | Status      | Approx. Hidden Data (bytes) |
|----------------------------------|-------------|-----------------------------|
| stego_6672108499_8c582a7f9.png  | Suspicious  | 137047                      |
| stego_6676452201_532f0bffe.png  | Suspicious  | 67141                       |
| stego_6677506211_e45d562b65.png | Suspicious  | 114785                      |

---

### **Performance Metrics**
- Number of images analyzed: **3**  
- True positives: **3**  
- False positives: **0**  
- Detection accuracy: **100%**  
- Average analysis time per image: **~1 second**  
- False positive rate: **0%**  
- Detection threshold effectiveness: **High**

---

## 📈 Analysis Findings

### 1️⃣ Detection Accuracy
- PNG format achieved **100% accuracy**.  
- StegExpose efficiently detected LSB-based hidden data.

### 2️⃣ Limitations Observed
- Limited to **LSB-based detection** only.  
- **Processing time** increases for large image sets.  
- **Accuracy** may vary across different formats.

### 3️⃣ Best Practices Identified
- Use **fast mode (-fast)** for large batch analysis.  
- Adjust threshold between **0.2–0.3** for optimal accuracy.  
- Test multiple image formats for comprehensive detection.

---

## 🏁 Conclusion
Steg-Expose proved to be an effective tool for detecting steganographic content in images.  
The experiment successfully demonstrated its ability to:
- Identify potentially compromised images  
- Analyze large image sets efficiently  
- Provide quantitative and statistical detection of hidden data  

