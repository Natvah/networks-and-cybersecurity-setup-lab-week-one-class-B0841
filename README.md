# networks-and-cybersecurity-setup-lab-week-one-class-B0841
Week One practical documenting the installation and configuration of Kali Linux using VirtualBox, including NAT networking, static IP addressing, Internet connectivity, shared folders, clipboard integration, drag-and-drop, snapshots, and troubleshooting.
# Week One Kali Lab – Troubleshooting Log

This file records the problems encountered during the setup, the checks performed, and the final outcomes.

## 1. Network Disconnected

- **Symptom:** Kali showed that the network connection was disconnected.
- **Checks:** VirtualBox Adapter 1, NAT Network selection, and the cable-connected option were checked.
- **Outcome:** The adapter was connected to `KaliLab` and network connectivity was restored.

## 2. Connection Activation Failed

- **Symptom:** A connection activation attempt failed.
- **Checks:** The connection profile name and Kali network interface were checked.
- **Outcome:** The network connection was successfully brought up after correcting the configuration.

## 3. Static IP and Gateway Verification

- **Symptom:** The IP address and gateway needed to be confirmed.
- **Commands used:**
  ```bash
  ip -br addr
  ip route
  ```
- **Final configuration:** `10.0.0.2/24`, gateway `10.0.0.1`, DNS `8.8.8.8`.
- **Outcome:** The address and default route were verified.

## 4. Connectivity Tests

Tests were separated to identify which part of the network was working.

```bash
ping -c 4 10.0.0.1
ping -c 4 8.8.8.8
ping -c 4 google.com
```

- Gateway test: successful.
- Internet IP test: successful.
- DNS/hostname test: successful.

## 5. Shared Folder Initially Not Visible

- **Symptom:** The shared folder was listed in VirtualBox, but Kali initially reported that the directory was not found.
- **Checks:** VirtualBox Shared Folders settings and the `vboxsf` module were checked.
- **Command used:**
  ```bash
  lsmod | grep vboxsf
  ```
- **Outcome:** The VirtualBox shared-folder driver was present, and the Windows Downloads folder was later accessible from Kali.

## 6. Final Verification

The lab was considered complete after confirming:

- Kali's static IPv4 address.
- Default gateway.
- Gateway connectivity.
- Internet connectivity.
- DNS resolution.
- Access to the Windows Downloads shared folder.
- Bidirectional clipboard and drag-and-drop.
- A saved VM snapshot.

## Reflection

The main lesson was to verify each configuration instead of assuming it worked. Checking the interface, route, gateway, Internet IP, DNS, and shared-folder driver separately made troubleshooting easier.

