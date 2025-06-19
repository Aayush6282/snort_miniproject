# 🛠️ Snort IDS Setup Guide (APT-Based Installation)

This guide walks you through installing and configuring **Snort 2.9** using `apt` on Ubuntu, and adding **custom rules** to detect **brute-force** and **port scan attacks**. This is ideal for a cybersecurity mini project setup.

---

## 📋 System Requirements

- Ubuntu 20.04 or later (or any Debian-based distro)
- Internet access
- Terminal and `sudo` privileges

---

## ✅ Step 1: Install Snort via APT

Open your terminal and run:

```bash
sudo apt update
sudo apt install snort

📌 During installation, when prompted for HOME_NET, you can enter:

192.168.0.0/16 or any

## ✅ Step 2: Verify Snort Installation

To confirm Snort is installed and check its version:
snort -V

✅ 3. Configure Snort

Edit main config:
sudo nano /etc/snort/snort.conf

✅ 4. Create Custom Rules

Edit local rules file:
sudo nano /etc/snort/rules/local.rules

✅ 5. Test Snort

Dry-run test:
sudo snort -T -c /etc/snort/snort.conf
If you see "Snort successfully validated the configuration", you're ready!

✅ 6. Run Snort in Live Mode

Use your interface (e.g. eth0):
sudo snort -i eth0 -c /etc/snort/snort.conf
Open another terminal and run test attacks.

✅ 7. Simulate Attacks

🔍 Port Scan:
nmap -sS <your IP>

✅ 8. View Snort Alerts

sudo cat /var/log/snort/snort.alert.fast
or
sudo tail -f /var/log/snort/snort.alert.fast

✅ 9. Analyze with tcpdump/wireshark

sudo tcpdump -nn -r logs/snort_capture.pcap
or
wireshark logs/snort_capture.pcap
 


