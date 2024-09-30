# Wi-Fi Hacking Tutorial Using Parrot OS with Airgeddon

## Overview

This tutorial provides a step-by-step guide on how to crack Wi-Fi passwords using the Airgeddon tool, which leverages vulnerabilities in WPA/WPA2 encryption. The process involves capturing WPA/WPA2 handshakes and then using them to crack the password.

### **Important**: Perform these actions only on networks you own or have explicit permission to test. Unauthorized access to networks is illegal and unethical.

## Requirements

1. **Hardware**:
   - Wireless Network Adapter with monitor mode and packet injection support (e.g., TP-Link adapter with Atheros chipset).

2. **Software**:
   - **Parrot Security OS** (or another Linux distribution for penetration testing).
   - **VirtualBox** (for running Parrot Security OS in a virtual environment).
   - **Airgeddon** (included in Parrot Security OS).

3. **Resources**:
   - Password dictionaries (e.g., RockYou password list).

## Setup

### 1. Install Parrot Security OS

1. Download [Parrot Security OS](https://www.parrotsec.org/download/) or the lighter version, Parrot Air.
2. Install VirtualBox from [Oracle](https://www.virtualbox.org/).
3. Create a new virtual machine in VirtualBox and use the downloaded Parrot Security OS image to install it.

### 2. Configure Wireless Adapter

1. Connect your wireless adapter to your computer.
2. In VirtualBox, go to `Devices` > `USB` and select your wireless adapter to ensure it's available in the virtual machine.

## Using Airgeddon to Capture and Crack Wi-Fi Passwords

1. **Boot Parrot Security OS** in VirtualBox.

2. **Start Airgeddon**:
   - Open a terminal and launch Airgeddon:

     ```bash
     sudo airgeddon
     ```

3. **Put Wireless Adapter into Monitor Mode**:
   - In Airgeddon, select **Option 2** to enable monitor mode:

     ```bash
     [2] Enable Monitor Mode
     ```

   - This will allow you to scan for networks.

4. **Scan for Targets**:
   - Select **Option 4** to explore available wireless networks:

     ```bash
     [4] Explore Wireless Networks
     ```

   - Pay attention to the data columns, particularly those indicating active connections (e.g., downloads or streaming).

   - Let the scan run for 20-30 seconds to gather a comprehensive list of networks. Press `Ctrl+C` to stop the scan.

![Screenshot 2024-09-09 070847](https://github.com/user-attachments/assets/9a52b5c0-dcb6-40c2-8cae-8b24a7f52757)

5. **Select Target Network**:
   - Choose a network from the list that has active clients.
   - Airgeddon will prompt you to select the network you want to target.

6. **Capture the Handshake**:
   - Move to the Handshake Tools menu by selecting **Option 5**:

     ```bash
     [5] Handshake Tools
     ```

   - Select **Option 1** to start capturing the handshake:

     ```bash
     [1] Capture WPA Handshake
     ```

   - Airgeddon will send deauthentication packets to disconnect clients and force them to reconnect, capturing the handshake in the process.

   - Once the handshake is captured, Airgeddon will save it to a file. Note the filename and location.

7. **Crack the Password**:
   - Go to **Option 6** to start the password cracking process:

     ```bash
     [6] Cracking WPA Handshake
     ```

   - Airgeddon will use the saved handshake file and your selected password dictionary to attempt to crack the password.

   - You can use a pre-existing dictionary file like RockYou or create a custom one. Make sure to specify the path to your dictionary file when prompted.

8. **Monitor Cracking Progress**:
   - Airgeddon will display the progress as it attempts to crack the password. This process may take seconds to minutes depending on the password's complexity.

## Conclusion

This guide demonstrates how to use Airgeddon to capture and crack WPA/WPA2 Wi-Fi passwords. Ensure that you use these techniques responsibly and only on networks you have permission to test.

## Disclaimer

This guide is for educational purposes only. Unauthorized access to computer networks is illegal and punishable by law. Always obtain explicit permission before testing any network.

## References

- [Parrot Security OS](https://www.parrotsec.org/)
- [Airgeddon](https://github.com/v1s1t0r1sh3r3/airgeddon)
- [RockYou Password List](https://github.com/brannondorsey/naive-hashcat/blob/master/rockyou.txt)
```
