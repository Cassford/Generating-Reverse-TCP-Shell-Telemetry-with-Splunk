# Generating-Reverse-TCP-Shell-Telemetry-with-Splunk

## Objective

The purpose of this project was to generate telemetry in Splunk using Sysmon and a reverse tcp shell payload
### Skills Learned

- Generating granular telemetry with Splunk and Sysmon for enhanced threat detection.
- Ability to regconize weak or inefficient controls.
- Enhanced knowledge of security vulnerabilities.
- Generic firewall configurations that often allow outbound connections while restricting incoming connections leave host vulnerable to 
  this payload as the payload initiates an outbound connection from the host.
  

### Tools Used

#### Splunk
###  Sysmon
###  Metasploit


## Steps
1. Created Reverse TCP Shell Payload and named it "Resume.pdf.exe".

![Reverse tcp shell pay load created](https://github.com/user-attachments/assets/f40ef298-3a5d-4d3c-b36f-2e6bcbfe669c)


2. Started Reverse TCP Handler on Attacker VM.

![Setting up handler on attacker machine](https://github.com/user-attachments/assets/08097927-d019-4fdc-982e-a51b4eba3dfa)


3. Started an HTTP server on Attacker VM to host the "Resume.pdf.exe" payload.

![Setting up an http server  on attacker machine](https://github.com/user-attachments/assets/524b2264-5f54-49fc-ba65-f102ec0ef08b)


4. Disabled Real Time Virus Protection To Allow the Defender VM to Execute the Payload. (Note: The purpose of this project was not focused on successful invasion without detection, but rather generating granular telemetry with Sysmon in Splunk.)

![Disabling Real Time Protection in Windows Defender](https://github.com/user-attachments/assets/d255af5c-6007-405c-b8de-f3382d250dcf) 


5. Edited the Input.conf File to Add Sysmon to Splunk on the Defender VM.

  ![Adding Sysmon to Splunk](https://github.com/user-attachments/assets/b9d671c0-8875-4f5a-be75-c450975e3613)



6. Created An Index in Splunk and named it Endpoint.

    ![endpoint index created](https://github.com/user-attachments/assets/0830d0b4-d970-4e7c-915e-2c33d77e1df6)


7. Accessed the Resume.pdf file on Attacker server through a web browser.

 ![Accessing the Resume pdf on the attacker server](https://github.com/user-attachments/assets/cc7eb059-cce9-452b-8a63-278b71194c38)


8. Downloaded The Payload.

   ![Downloaded payload showing as a pdf file](https://github.com/user-attachments/assets/d6d66785-8be4-456b-ab47-44a1cff79414)


9. Established Connection After Payload Execution

![Established connection after paylaod execution](https://github.com/user-attachments/assets/dff0489d-4a0a-4b67-ae2e-74d50956ac2d)


10. Session Opened After Payload Execution.

   ![Session opened after payload execution](https://github.com/user-attachments/assets/f7385584-1314-49c4-b55a-97aa7cc32062)


11. Proof of Malware Execution.

![Proof of malware execution](https://github.com/user-attachments/assets/65a3b18a-6eb6-4ba3-9536-2b57f8a4615a)


12. Perfomed Sample Commands on the Defender VM from the Attacker VM through in Shell in the Opened Session.

![Sample commands perfomed on the remote computer through the shell](https://github.com/user-attachments/assets/bd2ffa84-a575-4852-917a-d1cd7a9087f5)


13. Queried the Exploit with Splunk, on the Defender VM.

![Quering the the exploit](https://github.com/user-attachments/assets/efec3e34-c4ad-4368-a615-403f9cb20ea0)


14. Event Codes Associated with Exploit.

![Sysmon Event codes associted with it](https://github.com/user-attachments/assets/c1e456ed-734d-4bc0-9aba-01a0711d8bf3)


15. Results from Querying Resume.pdf.exe and Following Eventid 1.

![Circle parent process and process](https://github.com/user-attachments/assets/f1d6fb2c-a491-452c-892d-33c446c84f01)


16. Results from Querying the Process GUID. The Outcome Tells a Clearer Story of the Invasion and Shows Commands The Attacker Run Through the Remote Shell.

![Actual Final](https://github.com/user-attachments/assets/bc9d1aeb-b3c1-45b3-b1b0-e8c6501d054c)

