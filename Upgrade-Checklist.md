Windows 7 Enterprise → Windows 10 Enterprise

Clean-Install Upgrade Checklist (AD Domain, Client–Server Environment)

Context: Manual, PC-by-PC upgrades using a prepared bootable flash drive.
Role: First-level IT Support — perform checks, clean install, post-build config, app setup, validation, documentation.
Collaboration: Networks Team (IP/DHCP), Cloud Engineering (host naming), Security & Remediation (compliance validation before domain join).

0) Scope & Assumptions
 Target devices: Domain-joined Windows 7 Enterprise PCs (laptops/desktops).
 Upgrade method: Clean install of Windows 10 Enterprise (no in-place).
 Media: Pre-approved, bootable USB provided by central IT.
 Admin access: Temporary credentials for build steps / domain join (post-validation).
 Data: User data backed up to approved location (e.g., OneDrive/SharePoint/Network share).
 Security: Endpoint protection & compliance tools installed post-OS.

1) Roles & Escalations
Networks Team: IP/DHCP/VPN issues → Escalate with device MAC, switch/port (if known), error symptoms.
Cloud Engineering: Host naming convention & standards → Obtain/comfirm PC name before domain join.
Security & Remediation: Compliance validation gate → Green-light required before domain join.
IT Support Team Lead: Final report submission & closure.

2) Pre-Upgrade (T-1 to T-0)
Collect & Record (in upgrade template):
 User full name Job Role & department
 Asset Tag / Serial No. / Location
 Current Hostname / Planned Hostname (per Cloud Eng. standard)
 MAC Address (label or OS)
 Network type (LAN/Wi-Fi), Docking/Peripherals (printers/scanners)

Readiness Checks:
 Confirm backup completed (Documents, Desktop, PST if used, browser favorites, bespoke app data).
 Verify hardware OK (no SMART alerts, RAM errors; note Failed HDD → replace before proceeding).
 Capture installed business-critical apps (list versions & licenses if applicable).
 Confirm BitLocker/Drive Encryption status (if present, follow org policy to decrypt/suspend before wipe).
 Confirm user outage window & expectations.

Media & Power:
 Approved Windows 10 Enterprise bootable USB at hand.
 AC power connected; BIOS set to allow USB boot (Secure Boot/UEFI per standard).

3) Clean Install (T-0)
Boot to USB
 Insert media → Boot Menu → Select USB.

Disk Prep
 Delete old OS partitions; create new system partition per standard (GPT/UEFI).
 Proceed with Windows 10 Enterprise install.
OOBE / First Boot
 Create temporary local admin (per build standard).
 Set locale/timezone.
 Ensure device boots cleanly to desktop.

4) Base Configuration
Drivers & Updates
 Install chipset/NIC/graphics drivers (vendor packages).
 Run Windows Update to current baseline (repeat until no important updates remain).
 Confirm Device Manager → no unknown devices.

Core Agents & Security
 Install Endpoint Protection / compliance agents (per org standard).
 Install Remote Support/Management (e.g., SCCM/endpoint agent, remote connector).
 Verify security posture (local firewall on, Defender settings per policy).

Hostname & Network
 Rename PC as per Cloud Engineering standard → reboot.
 Connect to LAN → verify DHCP assignment (ipconfig /all).
 Basic connectivity test: ping internal.gateway / ping company.portal / web reachability.

5) Domain Join (Gate: Security & Remediation)
 Submit device details to Security & Remediation for validation (hostname, MAC, serial, agent status).
 On approval, join domain with authorized credentials.
 Reboot and log in with test domain account.
 Check GPO application:
 Confirm domain time sync & DNS resolution.

6) Enterprise Applications & Configuration
Core Productivity
 Microsoft 365 Apps (Office), Teams, OneDrive (sign-in + Known Folder Move if used).
 SharePoint access (map libraries if required), Outlook profile creation.
Line-of-Business (examples)
 BPMS desktop components
 BVN Biometric Capture / ZF1 Validation tools
 MoneyGram Client Payout / Western Union Applet
 Card Services (Mastercard/Visa/Verve) desktop tools
 Browser configs, SSL settings, hosts file entries (if standard requires)
 Bank security plug-ins / certificates as per playbook

Peripherals
 Printers/scanners drivers; test page & scan.
 Smart card readers / biometric devices (if applicable).

7) User Data Restore & Profile Setup
 Restore Documents/Desktop from OneDrive/SharePoint/network backup.
 Import PST / configure Outlook OST as needed.
 Restore browser favorites / password managers (per policy).
 Map network drives (GPO or manual per role).
 Configure VPN client (if required) and validate connection.

8) Validation & Sign-Off (with User)
Functional Checks
 Login with user domain account (no profile errors).
 Network/internet access stable; internal portals reachable.
 Core apps launch & authenticate; LoB apps perform business workflows.
 Printing/scanning OK; default printer set.
 GPO applied; Windows Activation confirmed; time sync OK.
 Device Manager clean; no update pending reboots.

Performance & Experience
 Boot time acceptable; no recurring errors in Event Viewer (System/Application).
 OneDrive/SharePoint syncing healthy.

User Acceptance
 Walkthrough completed; user confirms success.
 Capture User Sign-Off in online upgrade template.

9) Documentation & Handover
 Complete online upgrade template (fields: user, asset tag, serial, old/new OS, hostname, MAC, location, apps restored, issues, resolutions, sign-off time).
 Attach screenshots/logs where required (pre/post Device Manager, gpresult, activation, key app screens).
 Notify Team Lead, IT Support for review/closure.
 If any open issues → create/hand over tickets (Networks/Security/Apps) and record references.

10) Troubleshooting Quick Reference
Failed HDD → Replace drive; reinstall; restore from backup; note in report.
Domain Join Errors → Check DNS, time skew, network reachability; reset computer account in AD; retry.
Missing Drivers → Install vendor chipset/NIC first; re-scan; avoid generic drivers for LoB peripherals.
App Incompatibility → Check latest supported version; coordinate with vendor/App Support; document workaround.
User Data Issues → Validate backup source path; check permissions/ownership; recover from previous snapshot if available.

11) Continuous Improvement (Lessons Learned)
 Note repeated blockers (e.g., a driver package) → request gold image update.
 Propose pre-upgrade user comms template to reduce data surprises.
 Maintain a known-issues list and fixes to speed up next batches.  

Command Snippets used during the Project cycle:
ipconfig /all
ping <intranet-hostname>
gpupdate /force
gpresult /r
slmgr /xpr
gpupdate /force
gpresult /r
ipconfig /displaydns
ipconfig /registerdns
