# Active Directory Guide

[TR] [Türkçe README için buraya tıklayın](README-TR.md)

> *Notes, walkthroughs, TikTok clips, and scripts from my Windows Server 2022 Active Directory setup.*

---

## 📌 What's This Repo About?
This repo is my open notebook where I share:
- ✍️ **Lab Notes:** Step-by-step guides and commands I use along the way.
- 🎬 **Video Links:** TikTok clips tied directly to these lab steps.
- ⚡ **PowerShell Scripts:** Automation tools I'm planning to build (like bulk user creation & cleanup scripts).

---

## 🧪 Current Lab Setup
- **Hypervisor:** VirtualBox
- **Domain Controller:** Windows Server 2022 (`DC01`)
- **Domain:** `medipolis.local`
- **Clients:** Windows 10/11 (`CLIENT01`)

---

## 📚 Lab Notes & Progress

| Step | Topic / Module | Description & Breakdown | Notes (ENG / TR) | TikTok Clip |
| :---: | :--- | :--- | :---: | :---: |
| **00** | **Server IP & Network** | Static IP, Subnet Mask, Default Gateway, and DNS Loopback (`127.0.0.1`) setup[cite: 1, 2]. | [English](./00-server-ip-setup/server-ip-setup-eng.md) / [Türkçe](./00-server-ip-setup/server-ip-setup-tr.md) | [Watch 🎬](https://www.tiktok.com/@cozyxss/video/7688731015560334613?is_from_webapp=1&sender_device=pc) |
| **01** | **Hostname & Prep** | Server renaming (`DC01`), updates, and initial readiness checks. | [English](./01-hostname-update/01-hostname-update-eng.md) / [Türkçe](./01-hostname-update/01-hostname-update-tr.md)  | [Watch 🎬](https://www.tiktok.com/@cozyxss/video/7690963596574018822) |
| **02** | **AD DS Role Setup** | Active Directory Domain Services role installation via Server Manager. | *In Progress 🔄* | Coming Soon |
| **03** | **DC Promotion** | Promoting to Domain Controller, creating Forest (`medipolis.local`), DSRM password setup, and `SYSVOL` checks[cite: 1]. | *In Progress 🔄* | Coming Soon |
| **04** | **DNS & DHCP Config** | Forward/Reverse Lookup Zones, DHCP Scope (`192.168.10.X`), and DHCP Options (Router/DNS). | *Upcoming ⏳* | Coming Soon |
| **05** | **Client Prep & Network** | Windows 10/11 (`CLIENT01`) IP/DNS targeting and reachability testing (`nslookup` / `ping medipolis.local`)[cite: 1, 2]. | *Upcoming ⏳* | Coming Soon |
| **06** | **Client Domain Join** | Joining `CLIENT01` to `medipolis.local` domain and credentials verification[cite: 1]. | *Upcoming ⏳* | Coming Soon |
| **07** | **OU Hierarchy (AGDLP)** | Departmental Organizational Units architecture (`IT`, `HR`, `Finance`, `Computers`). | *Upcoming ⏳* | Coming Soon |
| **08** | **Users & RBAC Groups** | User creation, Role-Based Access Control (RBAC), and Security Groups (`SG_IT_Admins`). | *Upcoming ⏳* | Coming Soon |
| **09** | **Domain Login Test** | First domain user logon on client machine and local vs. domain profile checks. | *Upcoming ⏳* | Coming Soon |
| **10** | **Group Policy (GPO)** | GPMC rules: Desktop wallpaper enforcement, password policies, and screen saver lockouts. | *Upcoming ⏳* | Coming Soon |
| **11** | **Mapped Drives & Shares** | Share & NTFS permissions setup with automated drive mapping (`Z:\`) via GPO Preferences. | *Upcoming ⏳* | Coming Soon |
| **12** | **LAPS Integration** | Implementing Local Administrator Password Solution to dynamically rotate local admin passwords on endpoints. | *Upcoming ⏳* | Coming Soon |
| **13** | **AD Recycle Bin** | Enabling Active Directory Recycle Bin and demonstrating object restoration. | *Upcoming ⏳* | Coming Soon |
| **14** | **Secondary DC & FSMO** | Adding a secondary DC (`DC02`), checking replication status (`repadmin`), and understanding FSMO roles. | *Upcoming ⏳* | Coming Soon |
---

## ⚡ PowerShell & Automation *(Planned)*

Once the basic lab is up, I'll be adding custom PowerShell scripts here to automate daily AD tasks.

---

## 🌐 Find Me Around

- 🎵 **TikTok:** [tiktok.com/@cozyxss](https://www.tiktok.com/@cozyxss) (Bite-sized study clips & notes)
- ✍️ **Medium:** [medium.com/@cozyxss](https://medium.com/@cozyxss) (Detailed lab walkthroughs)
- 💼 **LinkedIn:** [linkedin.com/in/bbetulkaya](https://linkedin.com/in/bbetulkaya) (Career & finished projects)
