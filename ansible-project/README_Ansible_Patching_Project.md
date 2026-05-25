# README — Ansible Role-Based Linux Patch Management

## Project Purpose

This project automates Linux patching for Red Hat Enterprise Linux systems using Ansible roles.

It performs:
- Patch checking
- Patch installation using only RHEL repositories
- Conditional reboot
- Post-reboot validation
- Service validation

# Features

## Patch only from RHEL repositories

Uses:

--disablerepo="*"
--enablerepo="rhel*"

## Reboot only if required

Uses:
needs-restarting -r

## Dynamic service validation

Services are managed from:
services.yml

# Project Structure

ansible-project/

├── inventory/
│   └── hosts
├── group_vars/
│   └── all.yml
├── services.yml
├── Linux_patch_management.yml
└── roles/
    └── linux_patch/
        ├── defaults/
        │   └── main.yml
        ├── tasks/
        │   ├── main.yml
        │   ├── precheck.yml
        │   ├── patch.yml
        │   ├── reboot.yml
        │   └── validation.yml

# How to Run

cd ansible-project

ansible-playbook -i inventory/hosts Linux_patch_management.yml

# Future Changes

Add/remove services:
Modify services.yml

Change repos:
Modify group_vars/all.yml

Change reboot logic:
Modify roles/linux_patch/tasks/reboot.yml

# Advantages

- Modular
- Reusable
- Scalable
- Production friendly
- Easy maintenance
