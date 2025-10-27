# Experiment - 4
# Analyze Email Headers and Detect Email Spoofing using MHA (Mail Header Analyzer)  

## Aim  
To analyze email headers using the Mail Header Analyzer (MHA) tool and detect signs of email spoofing.  

---

## Description  
Email spoofing is a technique used by attackers to forge the sender’s address, making a message appear as though it came from a trusted source. By analyzing email headers, forensic investigators can identify the actual origin of an email and detect anomalies such as forged sender details, mismatched IP addresses, or unusual relay paths.  

The **Mail Header Analyzer (MHA)** is a tool that helps in decoding and analyzing raw email headers. It provides detailed insights into each hop the email took, the originating IP, authentication results (SPF, DKIM, DMARC), and potential signs of spoofing.  

---
## Tools & Equipment Used
 - Mail Header Analyzer (MHA)
 - Email Header
## MHA Link
[Click to redirect](https://mha.azurewebsites.net/)
---
## Procedure  

**Obtain the Raw Email Header**  
   - Open the suspicious email in your email client (e.g., Gmail, Outlook).  
   - Select the option to view the full message or email header.  
   - Copy the raw header content.  
![](<Output Screenshot\Exp4\Screenshot 2025-10-27 083932.png>)

     

**Access Mail Header Analyzer (MHA)**  
   - Open the Mail Header Analyzer tool (e.g., https://mha.azurewebsites.net/).
   
   - Paste the copied email header into the input box.  
![](<Output Screenshot\Exp4\Screenshot 2025-10-27 084026.png>)  

**Analyze the Header**  
   - Click **Analyze** to process the email header.  
   - The tool will display information such as:  
     - Source IP address of the sender  
     - Mail servers that relayed the message  
     - Authentication checks (SPF, DKIM, DMARC)  
![](<Output Screenshot\Exp4\Screenshot 2025-10-27 084047.png>)


**Check Authentication Results**  
   - Look for SPF, DKIM, and DMARC status.  
   - If any of them fail, it could be a sign of spoofing.  
 ![](<Output Screenshot\Exp4\Screenshot 2025-10-27 084109.png>) 

**Inspect Mail Path**  
   - Review the route taken by the email across multiple servers.  
   - Compare the originating IP and domain with the claimed sender’s address.  
!
**Detect Spoofing Indicators**  
   - Identify inconsistencies such as:  
     - Mismatched sender domain and IP address  
     - Failed SPF/DKIM/DMARC checks  
     - Abnormal relay servers not belonging to the claimed domain 
**Example of Malicious email header with abnormal delay**

![](<Output Screenshot/Exp4/Screenshot 2025-10-27 084122.png>)
---

## Result  
The email header was successfully analyzed using the Mail Header Analyzer. Spoofing indicators, such as mismatched sender details and failed authentication checks, were identified, helping in the detection of forged or malicious emails.  
