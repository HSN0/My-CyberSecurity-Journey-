# Initial Network Reconnaissance Report

## Assessment Information

Target:
Metasploitable2

Target IP:
192.168.56.101

Assessment Date:
29 June 2026

Assessor:
Hassan Hussain

---

## Objective

Identify live hosts and discover exposed TCP services on the target machine.

---

## Scope

One internal host:

192.168.56.101

---

## Methodology

Tool Used:

Nmap

Command:

nmap 192.168.56.101

---

## Findings

Host Status

The target host responded successfully and was online during testing.

Open Services Identified

* FTP (21)
* SSH (22)
* Telnet (23)
* SMTP (25)
* DNS (53)
* HTTP (80)
* RPCBind (111)
* NetBIOS (139)
* SMB (445)
* MySQL (3306)
* PostgreSQL (5432)
* VNC (5900)
* Additional services identified on ports 512, 513, 514, 1099, 1524, 2049, 2121, 6000, 6667, 8009 and 8180.

---

## Risk Summary

The target exposes numerous network services, increasing the available attack surface. Further service enumeration is recommended to determine versions, configurations and potential vulnerabilities.

---

## Recommendations

* Perform service version detection.
* Enumerate FTP, HTTP and SMB.
* Identify outdated software versions.
* Continue with vulnerability assessment.
