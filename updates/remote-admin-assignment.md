# Authorized Remote Administration & System Enumeration
SITC Diploma — Penetration Testing and Ethical Hacking module assignment

## Lab Setup
- Kali Linux + Windows 10 VMs on VirtualBox, connected via Internal Network
- Verified connectivity between both machines (`ifconfig` / `ipconfig`)

## Remote Access Method
- Generated a reverse TCP payload with `msfvenom` (Windows x64 target)
- Transferred payload to the Windows VM via USB (isolated lab environment)
- Configured Windows Defender exclusions to allow authorized payload execution
- Set up a Metasploit `multi/handler` listener on Kali matching payload/LHOST/LPORT
- Established a Meterpreter session on the Windows target

![Meterpreter session — Kali + Windows side by side]<img width="1920" height="1080" alt="meterpreter-session-live png" src="https://github.com/user-attachments/assets/3f0c9e3b-afd0-4dc9-9ba5-2fc7300dfcef" />

## System Enumeration
Collected remotely via Meterpreter/shell:
- Hostname, OS version (`sysinfo`)
- Architecture, domain, logged-on users

![System enumeration output]<img width="1805" height="877" alt="sysinfo-enumeration-output png" src="https://github.com/user-attachments/assets/add3c7da-20d0-418b-a5dc-0c8e8dcc6516" />

## Screenshot Capture
- Captured live remote desktop via Meterpreter `screenshot`

![Remote desktop screenshot capture]<img width="1804" height="783" alt="remote-desktop-screenshot-capture png" src="https://github.com/user-attachments/assets/3e5a3a4e-0621-46a6-9c8a-74eba73af42a" />

## Command Execution
- Ran administrative commands remotely: `net user`, `route print`

**Environment:** Fully isolated host-only/internal lab network — no external systems involved.

**Tools:** VirtualBox, Kali Linux, msfvenom, Metasploit Framework, Meterpreter


