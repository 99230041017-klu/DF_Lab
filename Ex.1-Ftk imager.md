# Ex.No.1    FTK Imager: A Forensic Imaging Tool Overview

## Acquiring Volatile Memory (RAM) Using FTK Imager
<br>


### Steps to Capture RAM Using FTK Imager
<br>

### 1. Run as Administrator
- Open **FTK Imager** with administrative privileges.  
- Right-click the FTK Imager icon and select **Run as administrator**.
<br>
<br>

![WhatsApp Image 2025-08-31 at 15 58 15_9ebf4c5d](https://github.com/user-attachments/assets/ad0262dc-dc5a-427a-9680-619b53da0415)

 
<br>
<br>

### 2. Initiate Memory Capture
- In the top menu bar, click **File → Capture Memory...** from the dropdown list.
  <br>
<br>

 ![WhatsApp Image 2025-08-31 at 15 12 35_c9ab6494](https://github.com/user-attachments/assets/b4d0208e-7b86-4bea-8687-fb6f3a512456)


<br>
<br>

### 3. Configure Destination
A dialog box will appear where you configure where and how the memory will be saved.

- **Destination Path:**  
  Click **Browse** to select a folder on an **external drive** (not the system drive).  

- **Destination Filename:**  
  You can keep the default `memdump.mem` or assign a more descriptive name.

- **Optional: Include pagefile.sys**  
  Check this box to capture `pagefile.sys`, which is virtual memory stored on the disk.  
  > Note: This may increase capture size and duration, but can contain valuable artifacts.

- **Optional: Create AD1 file**  
  Saves the memory dump in an AccessData-specific container file.  
  > Generally not necessary if using tools like **Volatility** for analysis.



<br>
<br>

![WhatsApp Image 2025-08-31 at 15 14 39_914b12e1](https://github.com/user-attachments/assets/ba234544-000d-47f6-bd84-d9872c2684b0)


 
<br>
<br>

### 4. Start Capture
- Click the **Capture Memory** button to begin acquisition.
<br>
<br>


![WhatsApp Image 2025-08-31 at 15 15 18_d95ef7cd](https://github.com/user-attachments/assets/af6cb605-8e9f-4885-b8bc-aaedaf9836be)


<br>
<br>

### 5. Wait for Completion
- A progress bar will indicate the capture status.  
- Capture time depends on the system’s RAM size.  
- Once finished, the memory dump file will be available in the destination folder.
---
<br>
<br>

## Acquiring Non-Volatile Memory (Disk Image) Using FTK Imager


### 1. Start the Process
- In FTK Imager, go to the top menu bar: **File → Create Disk Image...**.

<br>
<br>

![WhatsApp Image 2025-08-31 at 15 17 32_a4dda270](https://github.com/user-attachments/assets/af812e94-9196-47ca-bd0c-9380bca15af9)


<br>
<br>

### 2. Select Source Evidence Type
A window will appear asking you to choose the source type:

- **Physical Drive:** Images the entire disk, including all partitions, unallocated space, and the Master Boot Record (MBR).  
- **Logical Drive:** Images a specific partition (e.g., C: drive).  
- **Image File:** Converts or copies an existing image file.  
- **Contents of a Folder:** Creates an image of a specific folder only.  

> **Tip:** For full forensic imaging, select **Physical Drive**.
<br>
<br>
<p align="center">

![WhatsApp Image 2025-08-31 at 15 17 57_4e0cd2b6](https://github.com/user-attachments/assets/bcedcec1-7b01-4a3f-aad2-0a0f689d500c)

</p>
<br>
<br>

### 3. Select the Source Drive
- From the dropdown, choose the physical drive to image (connected via **write-blocker**).  
- Click **Finish**.
 <br>
<br>
<p align="center">
  
![WhatsApp Image 2025-08-31 at 15 18 36_41dea734](https://github.com/user-attachments/assets/36047364-3f01-49ec-83e2-0952614cc097)


</p>
<br>
<br>

### 4. Configure the Image Destination
- Click **Add...** in the "Create Image" window to define the image **format** and **destination**.
  <br>
<br>
<p align="center">
  
![WhatsApp Image 2025-08-31 at 15 19 09_0b992f9b](https://github.com/user-attachments/assets/ee44ef46-1d26-4286-a37f-c02aa4463473)

<br>

#### Options:

- **Image Type:**  
  - **E01 (EnCase Format):** Recommended; includes compression, metadata, and error-checking.  
  - **Raw (DD):** Bit-for-bit copy with no extra features.
<br>
<br>
<p align="center">
  
![WhatsApp Image 2025-08-31 at 15 20 02_b9c54d7d](https://github.com/user-attachments/assets/4b7b3652-136b-4544-b96d-75fc4e304576)


</p>
<br>
<br>

- **Fill in Evidence Item Information:**  
  - Enter case details, examiner name, and description.  
  - This information is stored in the image metadata (important for documentation).
 <p align="center">
   
![WhatsApp Image 2025-08-31 at 15 21 23_a58a5659](https://github.com/user-attachments/assets/92fb83e2-4667-422c-9b55-737f371607af)

</p>
<br>
<br>

- **Choose Destination Folder:**  
  - Must be a different drive from the source.  
  - Name the image file (e.g., `Case001_SuspectHDD`).  

- **Image Fragment Size:**  
  - Set a value to split the image into multiple parts.  
  - Set to `0` for a single image file.
  <br>
  <br>
  
<p align="center">
  
![WhatsApp Image 2025-08-31 at 15 22 26_f87b41ff](https://github.com/user-attachments/assets/ef068b6e-b0f6-4377-ae93-306240a51712)

</p>
<br>
<br>


### 5. Start the Imaging Process
- Click **Finish** to return to the "Create Image" screen.  
- **Check "Verify images after they are created"** to calculate hash values and ensure integrity.  
- Click **Start**.
  <br>
  <br>
  <p align="center">
 <img width="1088" height="734" alt="image" src="https://github.com/user-attachments/assets/14975271-7978-410f-b4f4-f2a63c328048" />

  <img width="1093" height="733" alt="image" src="https://github.com/user-attachments/assets/944f873f-a792-48ff-884c-d26afa6ec57b" />

</p>
<br>
<br>

### 6. Completion and Hash Verification
- The imaging process may take time depending on the drive size.  
- After completion, FTK Imager verifies the hashes automatically.  
- A final window shows **MD5** and **SHA1** hashes for both the source drive and image.  
- Matching hashes confirm the forensic image’s integrity.

---
## Notes

- Always use a **write-blocker** to prevent modifications to the evidence.  
- **Hash verification** is critical to maintain a chain of custody and admissibility in court.  
- **Image Fragmentation** is useful for large drives or storage limitations.
---

## References

- [FTK Imager Official Website](https://accessdata.com/product-download/ftk-imager-version-4-5)  
- FTK Imager Documentation
