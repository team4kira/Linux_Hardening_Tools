# Linux Hardening Tools

| Tool | Function |
| --- | --- |
| chkrootkit or rkhunter | Scans system for rootkits or malware |
| ufw | Uncomplicated Firewall (UFW), a frontend IP-Table. Host-based Firewall |
| Lynis | Security auditing tool. Check for potential vulnerabilities or misconfigurations that could be exploited by attackers |
| Fail2Ban | A log-parsing and intrusion prevention system (IPS). Can monitor system logs like those of SSH. Prevents brute-force attacks and blocks malicious IPs. |
| ClamAV | Anti-Virus software for Linux Machines |

Change Hostname

* Edit the **/etc/hostname** file. Should just have your current hostname in it, edit to new_hostname.
* Edit the **/etc/hosts**. Loocate the old_hostname and replace it with the new_hostname
* Enter following command: **sudo hostnamectl set-hostname new_hostname**
* Enter following command: **sudo reboot**
* After reboot use **sudo hostnamectl** to identify if changes were made correctly
  * Due to much of the commands require sudo, you may want to perform the following commands as a root user: sudo -i
