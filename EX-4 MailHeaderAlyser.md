# Ex.No.4   MHA (Mail Header Analyzer)
## Aim :
- The aim is to use a Mail Header Analyzer (MHA) to trace an email's origin and verify its authenticity by examining its header for signs of spoofing.
## Procedure
### Step 1: Get the Email Header
- First, you need to copy the full, raw header from the email.

- Gmail: Open the email, click the three dots (⋮), and select Show original.
<br>
<br>

![WhatsApp Image 2025-08-31 at 15 41 06_9fd755b3](https://github.com/user-attachments/assets/d8c59fdc-9d83-4843-a8d8-f7e50fa0843f)

<br>
<br>


- Select all the text in the header and copy it.

<br>

![WhatsApp Image 2025-08-31 at 15 40 42_857f4dc3](https://github.com/user-attachments/assets/9c44a911-245a-47aa-8506-fabadef8281f)

<br>
<br>

### Step 2: Use a Mail Header Analyzer (MHA)
- The easiest way to analyze the header is with an online tool.

- Navigate to a site like MXToolbox Email Header Analyzer.
 <br>
<br>

 ![WhatsApp Image 2025-08-31 at 15 42 45_08756eeb](https://github.com/user-attachments/assets/81a5934f-6d47-4eb7-8d8e-90735671b908)
 

<br>
<br>

- Paste the entire header you copied into the analysis box.
<br>
<br>

Click the "Analyze" button to get a parsed, easy-to-read report.
<br>
<br>

![WhatsApp Image 2025-08-31 at 15 44 01_99685174](https://github.com/user-attachments/assets/32385511-8dca-4e2a-924d-d9cdeee45516)

### Step 3: Analyze The Report
- This is the most critical step. In the analyzer's report, look for the SPF, DKIM, and DMARC results.
### Review the Overall Delivery Summary
- First, look at the high-level summary to get an immediate sense of the email's status.

- Check DMARC Compliance: The report shows the email is DMARC Compliant. This is the most important overall result.

- Check SPF Status: Both SPF Authenticated and SPF Alignment passed. This means the sending server was authorized.

- Check DKIM Status: DKIM Alignment passed, but DKIM Authenticated failed (❌). This is a critical finding and indicates a problem with the email's digital signature.
<br>
<br>

![WhatsApp Image 2025-08-31 at 15 45 00_cc8cb806](https://github.com/user-attachments/assets/71d0a8d1-03a9-47b3-9e4b-dd3f84d9c918)

<br>
<br>

### Investigate the SPF Record and Email Path
- Next, verify why the SPF check passed.

- Examine the SPF Record: The SPF record for the domain is v=spf1 include:mailgun.org ~all. This record explicitly authorizes servers from Mailgun to send emails on its behalf.

- Trace the Relay Information: The delivery path shows the email was sent from m241-136.mailgun.net.

- Conclusion: Since the email came from a Mailgun server, which is authorized in the SPF record, the SPF check passed.
  <br>
  <br>
  
![WhatsApp Image 2025-08-31 at 15 46 08_05880c63](https://github.com/user-attachments/assets/d8e61805-3cb2-4c15-8bcc-ffac174ebe10)

<br>
<br>

### Analyze the DKIM Failure

<br>

![WhatsApp Image 2025-08-31 at 15 46 30_49620210](https://github.com/user-attachments/assets/1754a065-bd49-45b6-ba58-e0460d925b7a)
