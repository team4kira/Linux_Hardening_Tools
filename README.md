# Linux Hardening Tools

| Tool | Function |
| --- | --- |
| chkrootkit or rkhunter | Scans system for rootkits or malware |
| ufw | Uncomplicated Firewall (UFW), a frontend IP-Table. Host-based Firewall |
| Lynis | Security auditing tool. Check for potential vulnerabilities or misconfigurations that could be exploited by attackers |
| Fail2Ban | A log-parsing and intrusion prevention system (IPS). Can monitor system logs like those of SSH. Prevents brute-force attacks and blocks malicious IPs. |
| ClamAV | Anti-Virus software for Linux Machines |

**Installation and Configurations:** 

| Processes | ClamAV |
| --- | --- |
| Summary | A program capable of Virus and Signature Based detection. Freshclam is the virus database and needs to be updated regularly for ClamAV to be effective |
| Installation | Run the following commands: <br> • sudo apt update <br> • sudo apt install clamav clamav-daemon <br> • sudo systemctl start clamav-freshclam <br> • sudo systemctl enable clamav-freshclam |
| Configuration | If Freshclam is not updating, perform the following: <br> • `ps aux \| grep freshclam` <br> • `sudo kill -9 <PID>` (Process ID is found in second column typically) <br> • freshclam.lock can be stuck, if you see this file in /var/log/clamav delete it <br> • Edit /etc/clamav/freshclam.conf make sure UpdateLogFile has this path /var/log/clamav/freshclam.log and under LogVerbose change status to True <br><br> Perform a scan: <br> • `sudo clamscan -r /<input_path>` ||

Change Hostname

* Edit the **/etc/hostname** file. Should just have your current hostname in it, edit to new_hostname.
* Edit the **/etc/hosts**. Locate the old_hostname and replace it with the new_hostname
* Enter following command: <br> `sudo hostnamectl set-hostname new_hostname`
* Enter following command: <br> `sudo reboot`
* After reboot use `sudo hostnamectl` to identify if changes were made correctly
  * Due to much of the commands require sudo, you may want to perform the following commands as a root user: sudo -i
