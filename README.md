# Linux System Management 3

SSH service validation - PXE basics - DNS

---

## Objectives

Verify and harden SSH server configuration
Understand PXE boot role and discovery process
Investigate DNS resolution settings and tools
Use `host`, `dig`, and `nslookup` to resolve names and test DNS behavior

---

## Tree

```
linux-system-management-3/
├── README.md
├── outputs/
│   ├── 01-sshd-status.txt
│   ├── 01b-sshd-port-check.txt
│   ├── 02-sshd-config.txt
│   ├── 03-pxe-theory.txt
│   ├── 04-resolv-nsswitch.txt
│   └── 05-dns-tools-output.txt
└── screenshots/
    ├── 01-sshd-status.png
    ├── 02-sshd-config.png
    ├── 03-pxe-theory.png
    ├── 04-resolv-nsswitch.png
    └── 05-dns-tools-output.png
```

---

## Execution

### 1. SSH Service Status & Port Validation

```bash
sudo systemctl status sshd
sudo ss -tuln | grep :22
sudo lsof -i :22
```
![01-sshd-status](screenshots/01-sshd-status.png)

---

### 2. SSHD Config Check (Hardened)

```bash
sudo grep -Ei 'permitrootlogin|passwordauthentication|port' /etc/ssh/sshd_config
```
![02-sshd-config](screenshots/02-sshd-config.png)

---

### 3. PXE Theory Notes (Manual)

What is PXE
How DHCP and TFTP are used
The boot process sequence

![03-pxe-theory](screenshots/03-pxe-theory.png)

---

### 4. DNS Resolution Files

```bash
cat /etc/resolv.conf
cat /etc/nsswitch.conf | grep hosts
```
![04-resolv-nsswitch](screenshots/04-resolv-nsswitch.png)

---

### 5. Name Resolution Tools

```bash
host google.com
dig google.com +short
nslookup google.com
```
 ![05-dns-tools-output](screenshots/05-dns-tools-output.png)

---

## Summary

✅ [`linux-system-management-1`](https://github.com/carlos-tech-ops/linux-system-management-1)  
✅ [`linux-system-management-2`](https://github.com/carlos-tech-ops/linux-system-management-2)  
✅ [`linux-system-management-3`](https://github.com/carlos-tech-ops/linux-system-management-3)
