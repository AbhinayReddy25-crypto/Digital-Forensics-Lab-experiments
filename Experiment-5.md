# Experiment - 5
# Use Autopsy to Create a Case and Import Evidence

## Aim
To learn how to create a new case in Autopsy Digital Forensics Tool and import digital evidence for analysis.

## Tools Used
- Autopsy 4.21.0 or later
- Sample digital evidence file (disk image, USB image, or any other supported format)

## Description
Autopsy is a popular open-source digital forensics platform used by law enforcement, military, and corporate examiners to investigate what happened on a computer. It has a graphical interface that allows forensic investigators to analyze disk images, perform timeline analysis, and recover deleted files.

## Procedure

1. **Launch Autopsy**
   - Open Autopsy digital forensics tool
   - Wait for the application to initialize
   
   
![alt text](<Output Screenshot/Exp5/Screenshot 2025-10-23 193917.png>)
   

2. **Create New Case**
   - Click on "Create New Case" option
   - Enter case name, base directory for case storage
   - Fill in optional case details (examiner name, case number, etc.)
   
    ![alt text](<Output Screenshot/Exp5/Screenshot 2025-10-23 193953.jpg>)

3. **Configure Case Database**
   - Select the database type (Single-user or Multi-user)
   - Choose the database location
   - Click "Next" to proceed
 

4. **Add Data Source**
   - Click "Add Data Source" in the main window
   - Select the type of data source (disk image, local drive, logical files)
   - Browse and select the evidence file
   
    ![alt text](<Output Screenshot/Exp5/Screenshot 2025-10-23 194006.png>)
  

5. **Configure Ingest Modules**
   - Select relevant ingest modules for analysis
     - Recent Activity
     - Hash Lookup
     - File Type Identification
     - Keyword Search
     - EXIF Parser
     - etc.
   - Configure settings for selected modules
   
   
   ![](<Output Screenshot/Exp5/Screenshot 2025-10-23 194505.png>)

6. **Start Analysis**
   - Review selected options
   - Click "Finish" to begin processing
   - Monitor ingest progress
   
   ![alt text](<Output Screenshot/Exp5/Screenshot 2025-10-23 194512.png>)
  ![alt text](<Output Screenshot/Exp5/Screenshot 2025-10-23 194545.png>)

## Result
After completing this experiment, you should be able to:
1. Successfully create a new case in Autopsy
2. Import digital evidence into the case
3. Configure appropriate ingest modules for analysis
4. Begin the forensic analysis process

The imported evidence will be ready for detailed forensic analysis using Autopsy's various tools and features. The case structure is now set up to maintain proper chain of custody and documentation of the investigation process.

![alt text](<Output Screenshot/Exp5/Screenshot 2025-10-23 210153.png>)