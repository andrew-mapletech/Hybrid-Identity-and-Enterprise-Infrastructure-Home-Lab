# 🔐 Hybrid Identity and Enterprise Infrastructure Lab

This project implements a **real-world hybrid enterprise IT environment** using on-premises infrastructure integrated with **Microsoft Entra ID (Azure Active Directory)** and modern **Zero Trust security architecture**.

It simulates how small-to-medium organizations run **Microsoft 365 with local servers**, enforcing secure identity, multi-factor authentication, conditional access, and least-privilege administration.

This environment is built on a **real Microsoft tenant** and a **real virtualization platform**, not a mock or simulator.

---

## 🎯 Project Goals

This lab was built to demonstrate hands-on skills in:

- Hybrid identity (Active Directory + Entra ID)  
- Zero Trust security design  
- Enterprise authentication & authorization  
- Secure remote access  
- On-prem and cloud integration  
- Centralized file storage and access control  
- Security monitoring and auditability  

---

## 🏗️ High-Level Architecture

| Layer | Technology |
|------|-----------|
| Hypervisor | Proxmox |
| Firewall | pfSense |
| Identity | Windows Server Active Directory |
| Cloud Identity | Microsoft Entra ID |
| Sync | Azure AD Connect |
| Storage | TrueNAS |
| Secure Access | Twingate VPN Connector (Proxmox LXC) |
| Security | MFA, Conditional Access, RBAC, PIM, Defender |

---

## 🧩 What Was Deployed

### On-Prem Infrastructure
- Windows Server 2025 Domain Controller  
- Linux internal application server  
- pfSense firewall virtual machine  
- TrueNAS storage server  
- Proxmox virtualization host  
- Twingate Connector deployed as a container  

### Cloud & Identity
- Microsoft Entra ID tenant  
- Azure AD Connect for hybrid sync  
- Hybrid users and groups  
- Entra ID SSO for Twingate  
- Entra ID authentication for Proxmox  

---

## 🔑 Hybrid Identity Implementation

A full **Active Directory domain** was created and synchronized to **Microsoft Entra ID** using Azure AD Connect.

This allows:
- Users to log into cloud services using on-prem credentials  
- Centralized identity management  
- Conditional Access and MFA enforcement  
- A single identity across on-prem and cloud  

Because Active Directory runs inside a VM, **Proxmox authentication is integrated with Entra ID**, allowing secure cloud-based SSO access to the virtualization platform.

---

## 🌍 Secure Remote Access (Twingate)

Secure remote access is implemented using **Twingate** with:

- A Twingate Connector deployed as a container inside the lab  
- Entra ID used as the Identity Provider  
- SSO and MFA enforced for remote users  
- Zero-trust access to internal services without exposing ports  

This allows users to securely access internal servers and applications from anywhere.

---

## 🔐 Zero Trust Security Design

Zero Trust is enforced by requiring verification for every access request, including:

- **Multi-Factor Authentication (MFA)**  
- **Conditional Access policies**  
- **Role-Based Access Control (RBAC)**  
- **Privileged Identity Management (PIM)**  
- **Microsoft Defender**  

No user or device is trusted by default.

---

## 🔥 Security Demonstration (Attack & Defense)

To demonstrate security awareness:
1. A weak admin role was intentionally created  
2. The risk of privilege escalation was demonstrated  
3. The environment was secured using:
   - Least privilege  
   - PIM  
   - MFA  
   - Conditional Access  

This shows both how attacks happen **and** how they are mitigated.

---

## 💾 Storage & Access Control

TrueNAS is integrated with Active Directory to provide:
- Domain-based file shares  
- Group-based access control  
- Snapshot backups  
- Restore testing  

---

## 📊 Monitoring & Logging

Security and access visibility is provided through:
- Entra ID sign-in logs  
- Audit logs  
- Microsoft Defender alerts  
- Windows event logs  
- Firewall logs  

---

## 📸 Proof of Implementation

This repository contains real screenshots and exports showing:
- Entra ID users and groups  
- Azure AD Connect sync status  
- Conditional Access policies  
- MFA enforcement  
- Twingate Entra ID SSO  
- Proxmox Entra ID login  
- Active Directory OU structure  
- TrueNAS domain integration  
- Defender alerts  

See the `/screenshots` folder for evidence.

---

## 📄 Full Documentation

A complete technical breakdown is available in:

`documentation/Hybrid_Zero_Trust_Lab.pdf`

This includes:
- Architecture  
- Identity design  
- Security controls  
- Remote access design  
- Storage configuration  
- Screenshots and logs  

---

## 🏆 What This Project Demonstrates

| Area | Skills Proven |
|------|--------------|
| Cloud | Entra ID, Conditional Access, SSO |
| Security | Zero Trust, MFA, PIM |
| Systems | Windows Server, Linux |
| Infrastructure | Proxmox, pfSense |
| Storage | TrueNAS, backups |
| Remote Access | Twingate VPN |
| Hybrid | On-prem + cloud integration |

---

## 🧠 Why This Matters

This project demonstrates the ability to design, deploy, secure, and operate a **real enterprise-grade hybrid IT environment** — including identity, security, cloud, storage, and secure remote access.

This is the same architecture used by modern organizations running Microsoft 365 with on-prem infrastructure.
