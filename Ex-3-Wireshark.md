#   Ex.No.3   Wireshark – Network Packet Capture and Analysis Tool


## Procedure: Capturing Plaintext Passwords

### Step 1: Start Capturing Packets
- First, open Wireshark. You will see a list of all available network interfaces (e.g., "Wi-Fi," "Ethernet").


- Select the interface your computer is using to connect to the internet (in this case, Wi-Fi).

  <br>
   <br>
  <p align="center">
  
 ![WhatsApp Image 2025-08-31 at 15 26 39_f48864a2](https://github.com/user-attachments/assets/869ba56d-7d0e-4c64-8146-6e2df6c815cc)

  </p>
  <br>
  <br>

- Click the blue shark fin icon 🦈 in the top-left corner to start the capture. Wireshark will immediately begin capturing all traffic passing through that interface.
 <br>
   <br>
  <p align="center">
    
  ![WhatsApp Image 2025-08-31 at 15 27 27_69575e85](https://github.com/user-attachments/assets/771786b3-f61b-4e09-bda7-af24fc7c33d7)

 </p>
  <br>
  <br>

  ### Step 2: Generate Login Traffic
  - Open a web browser and navigate to http://testphp.vulnweb.com/login.php.

- Enter any dummy credentials. For this example, we'll use:

   Username: testuser

   Password: password123

- Click the login button. The login will fail, but the data has already been sent across the network.

 <br>
   <br>
  <p align="center">
    
![WhatsApp Image 2025-08-31 at 15 32 06_1215b08f](https://github.com/user-attachments/assets/eb9d79a1-2a29-4103-b3e9-a3af2491418c)

 </p>
  
  
### step 3: Stop Capture and Filter Traffic

- Return to Wireshark and click the Stop button (the red square).

- In the display filter bar, you need to find the packet containing the login data. Since the form data was sent to the server, we will look for an HTTP POST request.

- Apply the following filter to find the exact packet and press Enter:

 <br>
   <br>
  <p align="center">
    
![WhatsApp Image 2025-08-31 at 15 33 28_5646d531](https://github.com/user-attachments/assets/19c8bd3d-2bc3-4009-9206-9376fb7cf4f6)

 </p>
  <br>
  <br>

### step 4: Inspect the Packet to Find Credentials 

- In the filtered packet list, you should see a packet with information like "POST /userinfo.php". Select this packet.

- In the Packet Details pane below the list, expand the following sections:

Hypertext Transfer Protocol

HTML Form URL Encoded

- Inside the "HTML Form URL Encoded" section, you will see the credentials you entered in plaintext.

 <br>
   <br>
  <p align="center">
    
 ![WhatsApp Image 2025-08-31 at 15 35 01_d1b14505](https://github.com/user-attachments/assets/ee89b98c-3bec-4643-b0ce-c3939356d7e0)

 </p>
  <br>
  <br>

---

## Result
The experiment successfully intercepts the login credentials in a human-readable format. The analysis of the captured POST packet reveals the plaintext data that was transmitted over the network:

This result confirms the inherent security flaw of the HTTP protocol. Any sensitive data sent over HTTP is transmitted openly, making it trivial to intercept.
