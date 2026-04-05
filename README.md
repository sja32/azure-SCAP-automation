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
