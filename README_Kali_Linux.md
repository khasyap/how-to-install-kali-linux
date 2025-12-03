# How to Install Kali Linux

This repository provides a complete guide for installing **Kali Linux** on your system using three different methods:
1. 🧩 **Using Virtual Machine (VM)**
2. 💽 **Dual Boot with Windows**
3. 🐉 **Using WSL (Windows Subsystem for Linux)**

---

## 🧩 1. Install Kali Linux on Virtual Machine (VM)

Installing Kali in a VM is the safest and most convenient way to use it without affecting your main operating system.

### 🔹 Requirements
- Virtualization enabled in BIOS (Intel VT‑x / AMD‑V)
- VirtualBox or VMware Workstation
- Minimum 20 GB free disk space and 2 GB RAM

### 🔹 Steps

1. Download the official **Kali Linux VM image** from [kali.org](https://www.kali.org/get-kali/#kali-virtual-machines)
2. Download and install your preferred virtualization software:
   - [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
   - [VMware Workstation Player](https://www.vmware.com/products/workstation-player.html)
3. Import the Kali image file (`.ova` for VirtualBox / `.vmx` for VMware)
4. Start the virtual machine and log in:
   ```bash
   Username: kali
   Password: kali
   ```
5. Update and upgrade your system inside Kali:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

✅ You’re ready to use Kali Linux safely inside a virtual environment!

---

## 💽 2. Install Kali Linux via Dual Boot (with Windows)

Dual booting gives you full hardware access and better performance than virtualization.

### 🔹 Requirements
- Minimum 25 GB of unallocated disk space
- USB drive (≥ 8 GB)
- Kali Linux ISO: [Download here](https://www.kali.org/get-kali/#kali-installer-images)
- Tool for making bootable USB: [Rufus](https://rufus.ie/) or [Balena Etcher](https://etcher.balena.io/)

### 🔹 Steps

1. **Create Bootable USB**
   - Use Rufus to write the Kali ISO to your USB drive.
   - Partition scheme: *GPT* for UEFI or *MBR* for BIOS systems.

2. **Prepare Windows**
   - Open *Disk Management* → Shrink volume to create free space for Kali (20 GB or more).

3. **Boot from USB**
   - Restart PC → Press *F12/F2/DEL* (depending on your system) to enter BIOS.
   - Disable *Secure Boot* and boot from your USB drive.

4. **Install Kali**
   - Choose *Graphical Install*.
   - Follow on-screen instructions (language, keyboard, user setup, etc.).
   - For partitioning, choose *Guided – use the largest continuous free space*.

5. **Install GRUB bootloader**
   - When asked, install GRUB to the main disk (e.g., `/dev/sda`).
   - Reboot after installation.

You’ll now see the **GRUB menu** on startup, allowing you to choose between **Windows** or **Kali Linux**.

---

## 🐉 3. Install Kali Linux using WSL (Windows Subsystem for Linux)

This is the easiest method if you just want to use Kali tools inside Windows without dual booting or a VM.

### 🔹 Requirements
- Windows 10 (v2004 or later) or Windows 11
- Admin access

### 🔹 Steps

1. **Enable WSL and Virtual Machine Platform**
   ```powershell
   wsl --install
   ```

2. **Install Kali Linux**
   ```powershell
   wsl --install -d kali-linux
   ```

   Or get it directly from the Microsoft Store:  
   👉 [Kali Linux – Microsoft Store](https://apps.microsoft.com/detail/9PKR34TNCV07)

3. **Set Up Kali**
   - Open Kali from Start Menu or run `kali` in PowerShell.
   - Create your username and password.

4. **Update the System**
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

5. **(Optional) Install GUI Desktop**
   ```bash
   sudo apt install kali-desktop-xfce -y
   sudo apt install xrdp -y
   sudo service xrdp start
   ```
   Then open **Remote Desktop (mstsc)** on Windows and connect to:
   ```
   localhost:3389
   ```

### ✅ Check WSL Status
```powershell
wsl --list --verbose
```

Expected output:
```
NAME           STATE           VERSION
* kali-linux   Running         2
```

---

## ⚖️ Comparison: VM vs Dual Boot vs WSL

| Feature | **Virtual Machine** | **Dual Boot** | **WSL** |
|----------|---------------------|----------------|----------|
| Performance | Moderate | High (Full Hardware Access) | Moderate |
| Safety | Very Safe | Risky if partitions misconfigured | Very Safe |
| GUI Support | Yes | Yes | Optional |
| Disk Usage | Uses virtual disk | Shared partitions | Light |
| Ideal For | Beginners, testing | Advanced users | Developers on Windows |

---

## 🔗 Official Resources

- 🐉 [Kali Linux Official Site](https://www.kali.org/)
- 💾 [Kali Linux Downloads](https://www.kali.org/get-kali/)
- 📚 [WSL Installation Guide (Microsoft)](https://learn.microsoft.com/en-us/windows/wsl/install)
- 💻 [Kali Linux WSL Documentation](https://www.kali.org/docs/wsl/wsl-pre-install/)

---

## 🧠 Author

**Konakalla Khasyap Surya Saketh**  
Full Stack Developer | Python Enthusiast | Cybersecurity Learner

[GitHub](https://github.com/khasyap)

---

## 📝 License

This guide is open-source and free to use or share.  
You may include it in your repositories with attribution.

---
