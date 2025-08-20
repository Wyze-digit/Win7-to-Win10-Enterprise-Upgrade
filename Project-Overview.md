# Win7-to-Win10-Enterprise-Upgrade Project
Step-by-step checklist and documentation for upgrading enterprise client computer systems from Windows 7 Enterprise to Windows 10 Enterprise, based on real IT support work experience at Access Bank Plc. 

📌 Project Overview
This repository documents the Windows 7 to Windows 10 Enterprise client upgrade project carried out in a large-scale financial institution (Access Bank).
The upgrade was done in a domain-based, client–server environment with strict IT governance (Active Directory, GPO policies, and cross-team collaboration). The project demonstrates how IT Support coordinates enterprise OS upgrades, handles first-line troubleshooting, and collaborates with Networks, Security, and Cloud Engineering teams to ensure smooth migration.

🛠 My Role & Responsibilities
As an IT Technical Support Officer, I was directly responsible for:
- Performing **pre-upgrade checks** (hardware validation - Verifying hardware health (HDD, RAM), user data review - Backup User data on temporary storage, compliance - Ensuring compliance with naming standards & upgrade readiness.)  
- Executed **upgrade installation** physically at user systems: Physically performing clean installs using prepared bootable USB.
- Conducted **post-upgrade troubleshooting** including: - Reinstalling/configuring business applications. - Applying upgrade checklist during manual PC-by-PC installations. - Driver issues. - Application reinstallation & configuration. - DHCP assignment verification. - Host renaming (per naming standards from Cloud Engineering). - Domain join (with admin credentials after Security validation). - Validating DHCP and network assignments (escalating IP issues to Networks Team). - Completed documentation and reported via official **upgrade template** to the IT Support Team Lead, IT Technical Support Representatives

---
🤝 Collaboration Across Teams
**Networks Team** → Escalated network/IP assignment issues including IP conflicts with other devices using STATIC IP PROTOCOL, PCs that could not pick IP addresses after DHCP enabled.  
**Cloud Engineering Team** → Obtained standardized naming conventions then applied it to each PC accross all branches.  
**Security & Remediation Team** → Validated compliance before domain joins.  
**Team Lead, IT Support** → Final upgrade reporting and handover. 

---
⚠️ Common Issues Encountered & Resolutions
**Failed HDD** → Escalated for hardware replacement  
**User data migration issues** → Assisted with data recovery and backups  
**Application incompatibility** → Coordinated with vendors for updates/replacements  
**Network/Domain rejoin failures** → Troubleshot with Networks Team and Security Team  

---
📊 Documentation Style
Followed a **professional upgrade playbook**  
Used an official **upgrade template** for each batch of upgraded systems  
Ensured consistent record-keeping for compliance and audits  

---
🎯 Lessons Learned
Importance of **collaboration across IT units** in enterprise rollouts  
Streamlining manual upgrades with checklists improves **speed and accuracy**  
Anticipating driver and app issues reduces post-upgrade downtime  

---
🚀 Key Takeaway
This project demonstrates my ability to deliver **large-scale IT service rollouts** with:  
- Strong troubleshooting skills  
- Structured documentation  
- Cross-team collaboration  
- Commitment to client satisfaction and operational excellence

📑 Upgrade Checklist
Covers:
Pre-upgrade hardware/user checks
Windows 10 Enterprise clean install process
Post-upgrade domain join and app configuration
Troubleshooting common issues

---
✅ Common Issues Encountered

HDD failures (replacement required). 
User data not properly backed up.
Application incompatibility with Windows 10.
Domain rejoin/network assignment errors.
Each issue was resolved by following escalation paths and applying IT support best practices. 

---
🚀 Relevance to Cloud/Systems Engineering
Although this project was focused on on-premise OS upgrades, the workflow is directly transferable to cloud migrations:
OS lifecycle management → Cloud VM migrations
Domain join & security validation → IAM & access controls
Manual installs → Automated deployments (future with Intune, SCCM, or CloudFormation)
Escalation to Networks → VPC/subnet/IPAM troubleshooting in AWS

----
🔗 Author
Wisdom Emmanuel (Wyze-digit). 
# 8+ years in IT Support (Banking & Enterprise IT environments). 
# Skilled in troubleshooting, cross-team collaboration, and system migrations.
# Preparing for AWS Solutions Architect Associate → moving towards Cloud & Systems Engineering career path.
