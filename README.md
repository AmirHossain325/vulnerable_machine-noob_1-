# vulnerable_machine-noob_1-

**Author:** Amir Hossain  
**Date:** 2025-09-30  
**Platform:** (Local VM/ Vulnhub )  
**Difficulty:** (Easy)

## TL;DR
It's a vulnerable ubuntu machine.Here our task is to access the machine and some have external info.
***Use vmware for setup.***
## Scope & Rules
- Target: `To takover the access`
## Methodology / Steps
1. **Information gathering**
   - Tools used: `nmap`, `netdiscover`.
   - Key findings: open ports 22,23 and so on.servece:FTP service with anonymous login possible,and also have Http port is open.

2. **Enumeration**
   - we found the ip with net discoverand than nmap scan we found a ftp vulnerability. 
   - when we saw the ftp service is on and anonymous port is possible we have a flag.

4. **Exploitation**
   **Step-by-step:**
1. **FTP login**
   - Connected via anonymous FTP and downloaded `cred.txt` and `welcome` files.
2. **Review credentials**
   - Opened `cred.txt` and found a username and password 
3. **Web access**
   - Logged into the web interface using the credentials found.
4. **Download/archive**
   - Clicked the `About Us` section and downloaded `.rar`.
5. **Extract**
   - Unrared the archive and discovered a `downloads/` directory with images and scripts.
6. **Image forensic**
   - Used `steghide` on some images and extracted additional files (e.g., `hint.py`, `user.txt`).
7. **Decode ciphertext**
   - `user.txt` contained Caesar cipher text — decoded via an online tool (or script) to obtain credentials for SSH.
8. **SSH login**
   - Used decoded credentials to login via SSH as a normal user.
9. **Privilege escalation**
   - Performed local enumeration, found a misconfigured `sudo`/SUID binary or script, and used it to get root.
10. **Root proof**
   - Switched to root and found `root.txt` — it was Base64 encoded; decoded and retrieved the root flag.
                                                        **  Than its finish!!**


## Proof 1:for ftp login: / Screenshots<img width="1419" height="689" alt="Screenshot 2025-09-30 123239" src="https://github.com/user-attachments/assets/269769a1-e588-4d37-a61b-2d3525c6ffb8" />
2:<img width="1308" height="443" alt="Screenshot 2025-09-30 123335" src="https://github.com/user-attachments/assets/06deb93b-415a-427f-8fdb-91e316a3b616" />
3.<img width="1180" height="700" alt="Screenshot 2025-09-30 123933" src="https://github.com/user-attachments/assets/83328f24-54d9-40ec-8d04-ed6836eefbde" />
4.<img width="1248" height="732" alt="Screenshot 2025-09-30 124007" src="https://github.com/user-attachments/assets/57385f2d-041b-4946-9b30-1cb962447c4a" />
5.<img width="1125" height="636" alt="Screenshot 2025-09-30 124537" src="https://github.com/user-attachments/assets/2b7962ba-22e2-40e3-9954-c402b324e2fa" />
6.<img width="755" height="403" alt="Screenshot 2025-09-30 124638" src="https://github.com/user-attachments/assets/bea00d53-ad38-437e-af25-42924cf912d1" />
7.<img width="1479" height="421" alt="Screenshot 2025-09-30 124848" src="https://github.com/user-attachments/assets/41d04715-dd10-4f82-93a3-9726b7e08586" />
8.<img width="1016" height="601" alt="Screenshot 2025-09-30 130404" src="https://github.com/user-attachments/assets/49de24e1-29f4-4339-bf81-3ece6ad4f2ed" />
9.<img width="1432" height="821" alt="Screenshot 2025-09-30 130543" src="https://github.com/user-attachments/assets/f1191bab-054f-4ea6-8c9e-7fea7fc1f532" />

10.<img width="1196" height="702" alt="Screenshot 2025-09-30 130951" src="https://github.com/user-attachments/assets/15168924-664d-4201-89a6-877783209647" />

11.<img width="1300" height="723" alt="Screenshot 2025-09-30 131002" src="https://github.com/user-attachments/assets/3c1b4fb0-e579-4653-9ffa-95326938c314" />

12.<img width="1305" height="730" alt="Screenshot 2025-09-30 131605" src="https://github.com/user-attachments/assets/ac97e2a0-a6e7-4a14-a98e-9a5a2b489c7b" />

13.<img width="649" height="243" alt="Screenshot 2025-09-30 132157" src="https://github.com/user-attachments/assets/695952ff-2879-408c-871c-1c4514790ce5" />









