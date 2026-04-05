# Azure SCAP Automation

Automated STIG compliance scanning and remediation for Azure Linux virtual machines using OpenSCAP and Ansible.

---

## 🚀 Overview

This project implements a repeatable security and compliance workflow for Linux-based Azure virtual machines. It leverages OpenSCAP for DISA STIG-aligned compliance scanning and Ansible for orchestration and OS hardening.

The goal is to simulate a real-world enterprise process for assessing, remediating, and validating system security posture in a cloud environment.

---

## 🧱 Architecture

- Azure IaaS Linux VM (NGINX web server)
- Ansible Control Node (on-prem lab environment)
- OpenSCAP (STIG compliance scanning)
- File Share (artifact storage)
- STIG Viewer (checklist validation and documentation)

---

## 🔄 Workflow

1. Provision Azure VM (Terraform or manual deployment)
2. Execute OpenSCAP scan via Ansible
3. Generate compliance artifacts:
   - `results.xml` (XCCDF results)
   - `report.html` (human-readable report)
4. Transfer artifacts to centralized share
5. Import SCAP results into STIG Viewer
6. Apply remediation playbook (Ansible)
7. Re-run scan to validate compliance improvements

---

## 🛠️ Tools & Technologies

- Microsoft Azure (IaaS)
- Ansible
- OpenSCAP
- NGINX
- Linux (Ubuntu / RHEL)
- STIG Viewer

---

## 📂 Project Structure

azure-SCAP-automation/
├── inventory/
├── group_vars/
├── playbooks/
├── roles/
├── artifacts/
├── docs/
├── scripts/
└── README.md

---

## ⚙️ Getting Started

### Clone repo

git clone git@github.com
:sja32/azure-SCAP-automation.git


### Run scan

ansible-playbook -i inventory/inventory.ini playbooks/scan-linux-stig.yml


### Run remediation

ansible-playbook -i inventory/inventory.ini playbooks/remediate-linux-baseline.yml


---

## 📊 Output

Artifacts generated:

- results.xml  
- report.html  
- oscap-console.txt  

---

## 🔐 Security Considerations

- Verify SSH key authentication before disabling passwords  
- Restrict SSH access to trusted IPs  
- Validate firewall rules before enabling  

---

## 📘 Lessons Learned

- SCAP results can be imported into STIG Viewer  
- Not all controls map perfectly  
- Automation reduces manual effort  

---

## 🔮 Future Enhancements

- Role-based Ansible design  
- Scheduled scans  
- Azure Policy integration  
- NGINX hardening validation  

---

## 👤 Author

Sharod Allen  
Information Systems Security Engineer (ISSE)

---

## 📌 Summary

This project demonstrates:

- Automated compliance scanning  
- Security baseline enforcement  
- Cloud security integration  
- Audit-ready artifact generation  
