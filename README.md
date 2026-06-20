# Ansible Server Hardening

Automated Linux server hardening using Ansible, orchestrated via Jenkins CI/CD pipeline with GitHub as version control.

## Tech Stack
- Ansible — Infrastructure automation playbooks
- Jenkins — CI/CD pipeline orchestration
- GitHub — Version control (IaC)
- AlmaLinux 9 — Target server environment

## What This Automates
- System package updates
- Firewalld installation and enablement
- Timezone configuration (Asia/Kolkata)
- Standard admin user creation
- Root SSH login disabled
- Fail2ban installation for brute-force protection

## Pipeline Flow
Push to GitHub → Jenkins detects change → Ansible playbook runs → Server hardened automatically

## How to Run Manually
ansible-playbook -i inventory/hosts.ini playbooks/harden.yml
