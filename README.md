# Linux-CLI-Practice-Lab
# 50 Linux Commands Practice Lab

This repository documents my hands-on Linux command-line practice from basic system checks to real DevOps workflows.  
Each command includes a short purpose, an example command, and a screenshot reference from the lab.

## Project Goal

The goal of this lab was to build Linux confidence by practicing commands one by one and chaining them together like real-world troubleshooting and administration tasks.

## Skills Practiced

- Linux system information
- Filesystem navigation
- File creation, copying, moving, and deletion
- Redirection and append operators
- Permissions and ownership
- Process monitoring
- Networking and DNS troubleshooting
- Archives and compression
- Services with `systemctl`
- Logs with `journalctl`
- Cron job automation

---

## Commands 1–10: System Basics and File Output

### 1. `whoami && id`

**Description:** Shows the current logged-in user and user/group IDs.

**Example:**
```bash
whoami && id
```

**Screenshot:**
```md
![whoami and id](50-Linux-%20Commands/01-whoami%20%26%26%20id.png)
```

---

### 2. `uname -a && cat /etc/os-release`

**Description:** Displays kernel, architecture, and Linux distribution details.

**Example:**
```bash
uname -a && cat /etc/os-release
```

**Screenshot:**
```md
![uname os release](50-Linux-%20Commands/02-uname-os-release.png)
```

---

### 3. `uptime && nproc && free -h`

**Description:** Checks server uptime, CPU count, and memory usage.

**Example:**
```bash
uptime && nproc && free -h
```

**Screenshot:**
```md
![uptime nproc free](50-Linux-%20Commands/03-uptime-nproc-free.png)
```

---

### 4. `df -h && du -sh /var/log`

**Description:** Shows disk usage and the size of a directory.

**Example:**
```bash
df -h && du -sh /var/log
```

**Screenshot:**
```md
![df du disk](50-Linux-%20Commands/04-df-du-disk.png)
```

---

### 5. `ps aux | grep ssh`

**Description:** Lists processes and filters for SSH-related processes.

**Example:**
```bash
ps aux | grep ssh
```

**Screenshot:**
```md
![ps grep ssh](50-Linux-%20Commands/05-ps-grep-ssh.png)
```

---

### 6. `ps aux | grep ssh | grep -v grep`

**Description:** Filters SSH processes while removing the grep command from the output.

**Example:**
```bash
ps aux | grep ssh | grep -v grep
```

**Screenshot:**
```md
![ps grep v grep](50-Linux-%20Commands/06-ps-grep-v-grep.png)
```

---

### 7. `ls /var/log | head`

**Description:** Lists log files and limits output to the first few lines.

**Example:**
```bash
ls /var/log | head
```

**Screenshot:**
```md
![ls head var log](50-Linux-%20Commands/07-ls-head-var-log.png)
```

---

### 8. `mkdir lab && cd lab && touch file.txt && ls`

**Description:** Creates a directory, enters it, creates a file, and lists the result.

**Example:**
```bash
mkdir lab && cd lab && touch file.txt && ls
```

**Screenshot:**
```md
![mkdir cd touch ls](50-Linux-%20Commands/08-mkdir-cd-touch-ls.png)
```

---

### 9. `pwd && ls`

**Description:** Prints the current working directory and lists files inside it.

**Example:**
```bash
pwd && ls
```

**Screenshot:**
```md
![pwd ls](50-Linux-%20Commands/09-pwd-ls.png)
```

---

### 10. `echo "Hello Linux" > file.txt && cat file.txt`

**Description:** Writes text into a file and displays the file content.

**Example:**
```bash
echo "Hello Linux" > file.txt && cat file.txt
```

**Screenshot:**
```md
![echo cat redirect](50-Linux-%20Commands/10-echo-cat-redirect.png)
```

---

## Commands 11–20: File Management and Text Processing

### 11. `echo "Second line" >> file.txt && cat file.txt`

**Description:** Appends text to an existing file and displays the updated content.

**Example:**
```bash
echo "Second line" >> file.txt && cat file.txt
```

**Screenshot:**
```md
![echo append cat](50-Linux-%20Commands/11-echo-append-cat.png)
```

---

### 12. `cp file.txt backup.txt && ls`

**Description:** Copies a file and lists the directory to confirm the backup.

**Example:**
```bash
cp file.txt backup.txt && ls
```

**Screenshot:**
```md
![cp backup ls](50-Linux-%20Commands/12-cp-backup-ls.png)
```

---

### 13. `mv backup.txt renamed.txt && ls`

**Description:** Renames or moves a file and confirms the change.

**Example:**
```bash
mv backup.txt renamed.txt && ls
```

**Screenshot:**
```md
![mv rename ls](50-Linux-%20Commands/13-mv-rename-ls.png)
```

---

### 14. `mkdir logs && touch logs/app.log && ls logs`

**Description:** Creates a logs directory and a sample log file.

**Example:**
```bash
mkdir logs && touch logs/app.log && ls logs
```

**Screenshot:**
```md
![mkdir touch logs](50-Linux-%20Commands/14-mkdir-touch-ls-logs.png)
```

---

### 15. `rm renamed.txt && ls`

**Description:** Deletes a file and lists the directory to confirm removal.

**Example:**
```bash
rm renamed.txt && ls
```

**Screenshot:**
```md
![rm file ls](50-Linux-%20Commands/15-rm-file-ls.png)
```

---

### 16. `mkdir project && cd project && echo "app started" > app.log && cat app.log`

**Description:** Creates a project folder, writes a log message, and reads the file.

**Example:**
```bash
mkdir project && cd project && echo "app started" > app.log && cat app.log
```

**Screenshot:**
```md
![mkdir cd echo cat](50-Linux-%20Commands/16-mkdir-cd-echo-cat.png)
```

---

### 17. `cd .. && pwd && ls`

**Description:** Moves back to the parent directory, prints the location, and lists files.

**Example:**
```bash
cd .. && pwd && ls
```

**Screenshot:**
```md
![cd parent pwd ls](50-Linux-%20Commands/17-cd-parent-pwd-ls.png)
```

---

### 18. `touch file1 file2 file3 && ls -l`

**Description:** Creates multiple files and shows detailed file information.

**Example:**
```bash
touch file1 file2 file3 && ls -l
```

**Screenshot:**
```md
![multi files ls l](50-Linux-%20Commands/18-multi-files-ls-l.png)
```

---

### 19. `echo -e "error\nsuccess\nwarning" > app.log && cat app.log`

**Description:** Creates a multi-line log file and displays it.

**Example:**
```bash
echo -e "error\nsuccess\nwarning" > app.log && cat app.log
```

**Screenshot:**
```md
![multi line echo cat](50-Linux-%20Commands/19-multi-line-echo-cat.png)
```

---

### 20. `grep error app.log && echo "error found"`

**Description:** Searches for a keyword in a file and chains a success message.

**Example:**
```bash
grep error app.log && echo "error found"
```

**Screenshot:**
```md
![grep logic operator](50-Linux-%20Commands/20-grep-logic-operator..png)
```

---

## Commands 21–30: Permissions, Ownership, and Processes

### 21. `chmod +x testing.sh && ./testing.sh`

**Description:** Makes a script executable and runs it.

**Example:**
```bash
echo 'echo "Hello DevOps"' > testing.sh && chmod +x testing.sh && ./testing.sh
```

**Screenshot:**
```md
![chmod executable script](50-Linux-%20Commands/21-chmod-executable-script-chain.png)
```

---

### 22. `chmod 644 testing.sh && ls -l testing.sh`

**Description:** Sets file permissions so owner can read/write, group and others can read only.

**Example:**
```bash
chmod 644 testing.sh && ls -l testing.sh
```

**Screenshot:**
```md
![chmod 644](50-Linux-%20Commands/22-chmod-644-permissions-chain.png)
```

---

### 23. `chmod 755 testing.sh && ls -l testing.sh && ./testing.sh`

**Description:** Gives execute permission back so the script can run again.

**Example:**
```bash
chmod 755 testing.sh && ls -l testing.sh && ./testing.sh
```

**Screenshot:**
```md
![chmod 755](50-Linux-%20Commands/23-chmod-755-executable-chain.png)
```

---

### 24. `chown $USER:$USER testing.sh && ls -l testing.sh`

**Description:** Changes file ownership to the current user and group.

**Example:**
```bash
chown $USER:$USER testing.sh && ls -l testing.sh
```

**Screenshot:**
```md
<!-- Add screenshot here when uploaded -->
![chown owner group](50-Linux-%20Commands/24-chown-owner-group-chain.png)
```

---

### 25. `adduser devopsuser && su - devopsuser`

**Description:** Creates a new Linux user and switches into that user.

**Example:**
```bash
adduser devopsuser
su - devopsuser
```

**Screenshot:**
```md
![create switch linux user](50-Linux-%20Commands/25-create-and-switch-linux-user.png)
```

---

### 26. `chown devopsuser:devopsuser testing.sh && ls -l testing.sh`

**Description:** Transfers ownership of a file to another Linux user.

**Example:**
```bash
chown devopsuser:devopsuser testing.sh && ls -l testing.sh
```

**Screenshot:**
```md
![chown transfer ownership](50-Linux-%20Commands/26-chown-transfer-ownership-chain.png)
```

---

### 27. `ps aux | head`

**Description:** Shows running processes and limits output to the first few lines.

**Example:**
```bash
ps aux | head
```

**Screenshot:**
```md
![ps aux head](50-Linux-%20Commands/27-ps-aux-head-processes-chain.png)
```

---

### 28. `ps aux | grep bash | grep -v grep`

**Description:** Searches for Bash processes while removing the grep process itself.

**Example:**
```bash
ps aux | grep bash | grep -v grep
```

**Screenshot:**
```md
![ps grep bash](50-Linux-%20Commands/28-ps-grep-bash-process-filter-chain.png)
```

---

### 29. `top -n 1 | head`

**Description:** Shows system resource usage once and limits output for readability.

**Example:**
```bash
top -n 1 | head
```

**Screenshot:**
```md
![top system monitor](50-Linux-%20Commands/29-top-system-monitor-chain.png)
```

---

### 30. `kill -l`

**Description:** Lists all available Linux kill signals.

**Example:**
```bash
kill -l
```

**Screenshot:**
```md
![kill signals](50-Linux-%20Commands/30-kill-signals-list-chain.png)
```

---

## Commands 31–40: Networking and DNS Troubleshooting

### 31. `curl https://example.com`

**Description:** Makes a web request and prints the response in the terminal.

**Example:**
```bash
curl https://example.com
```

**Screenshot:**
```md
![curl web request](50-Linux-%20Commands/31-curl-web-request-chain.png)
```

---

### 32. `wget https://example.com`

**Description:** Downloads a web page or file from the internet.

**Example:**
```bash
wget https://example.com
```

**Screenshot:**
```md
![wget download](50-Linux-%20Commands/32-wget-download-file-chain.png)
```

---

### 33. `ping -c 4 google.com`

**Description:** Tests network connectivity and latency to a host.

**Example:**
```bash
ping -c 4 google.com
```

**Screenshot:**
```md
![ping connectivity](50-Linux-%20Commands/33-ping-network-connectivity-chain.png)
```

---

### 34. `ip a`

**Description:** Displays network interfaces and IP addresses.

**Example:**
```bash
ip a
```

**Screenshot:**
```md
![ip address](50-Linux-%20Commands/34-ip-address-network-interface-chain.png)
```

---

### 35. `netstat -tulnp`

**Description:** Shows listening TCP/UDP ports and related processes.

**Example:**
```bash
netstat -tulnp
```

**Screenshot:**
```md
![netstat ports](50-Linux-%20Commands/35-netstat-listening-ports-chain.png)
```

---

### 36. `ss -tulnp`

**Description:** Modern replacement for `netstat` to view listening ports.

**Example:**
```bash
ss -tulnp
```

**Screenshot:**
```md
![ss ports](50-Linux-%20Commands/36-ss-listening-ports-chain.png)
```

---

### 37. `dig google.com`

**Description:** Performs a detailed DNS lookup for a domain.

**Example:**
```bash
dig google.com
```

**Screenshot:**
```md
![dig dns lookup](50-Linux-%20Commands/37-dig-dns-lookup-chain.png)
```

---

### 38. `nslookup google.com`

**Description:** Performs a simple DNS lookup for a domain.

**Example:**
```bash
nslookup google.com
```

**Screenshot:**
```md
![nslookup dns](50-Linux-%20Commands/38-nslookup-dns-resolution-chain.png)
```

---

### 39. `traceroute google.com`

**Description:** Shows the network path packets take to reach a destination.

**Example:**
```bash
traceroute google.com
```

**Screenshot:**
```md
![traceroute path](50-Linux-%20Commands/39-traceroute-network-path-chain.png)
```

---

### 40. `hostname -I`

**Description:** Quickly displays the machine’s assigned IP addresses.

**Example:**
```bash
hostname -I
```

**Screenshot:**
```md
![hostname ip](50-Linux-%20Commands/40-hostname-ip-address-chain.png)
```

---

## Commands 41–50: Logs, Archives, Services, and Automation

### 41. `tar -cvf logs.tar logs/`

**Description:** Creates an archive from a logs directory.

**Example:**
```bash
mkdir -p logs && echo "app started" > logs/app.log && echo "error found" > logs/error.log && tar -cvf logs.tar logs/
```

**Screenshot:**
```md
![tar create](50-Linux-%20Commands/41-tar-create-logs-archive-chain.png)
```

---

### 42. `tar -xvf logs.tar && ls`

**Description:** Extracts a tar archive and verifies the files.

**Example:**
```bash
tar -xvf logs.tar && ls
```

**Screenshot:**
```md
![tar extract](50-Linux-%20Commands/42-tar-extract-archive-chain.png)
```

---

### 43. `gzip index.html && ls`

**Description:** Compresses a file using gzip.

**Example:**
```bash
gzip index.html && ls
```

**Screenshot:**
```md
![gzip file](50-Linux-%20Commands/43-gzip-file-compression-chain.png)
```

---

### 44. `gunzip index.html.gz && ls`

**Description:** Decompresses a gzip file back to the original file.

**Example:**
```bash
gunzip index.html.gz && ls
```

**Screenshot:**
```md
![gunzip file](50-Linux-%20Commands/44-gunzip-file-decompression-chain.png)
```

---

### 45. `systemctl status ssh`

**Description:** Checks the status of the SSH service.

**Example:**
```bash
systemctl status ssh
```

**Screenshot:**
```md
![systemctl ssh status](50-Linux-%20Commands/45-systemctl-service-status-chain.png)
```

---

### 46. `systemctl start nginx && systemctl status nginx`

**Description:** Starts the NGINX service and verifies it is running.

**Example:**
```bash
systemctl start nginx && systemctl status nginx
```

**Screenshot:**
```md
![systemctl start nginx](50-Linux-%20Commands/46-systemctl-start-nginx-chain.png)
```

---

### 47. `systemctl stop nginx && systemctl status nginx`

**Description:** Stops the NGINX service and verifies it is inactive.

**Example:**
```bash
systemctl stop nginx && systemctl status nginx
```

**Screenshot:**
```md
![systemctl stop nginx](50-Linux-%20Commands/47-systemctl-stop-nginx-chain.png)
```

---

### 48. `journalctl -xe | head`

**Description:** Views recent system logs and limits output for readability.

**Example:**
```bash
journalctl -xe | head
```

**Screenshot:**
```md
![journalctl logs](50-Linux-%20Commands/48-journalctl-system-logs-chain.png)
```

---

### 49. `crontab -l`

**Description:** Lists scheduled cron jobs for the current user.

**Example:**
```bash
crontab -l
```

**Extra cron example:**
```bash
* * * * * echo "Cron worked at $(date)" >> /tmp/cron-demo.log
```

**Screenshot:**
```md
![cronjob auto log](50-Linux-%20Commands/49-cronjob-auto-log-chain.png)
```

---

### 50. `echo "DevOps Linux Practice Complete" && uname -a && uptime`

**Description:** Final validation command showing a completion message, system kernel info, and uptime.

**Example:**
```bash
echo "DevOps Linux Practice Complete" && uname -a && uptime
```

**Screenshot:**
```md
![linux practice complete](50-Linux-%20Commands/50-devops-linux-practice-complete-chain.png)
```

---

## Cron Job Bonus Screenshot

```md
![cron jobs](50-Linux-%20Commands/cron%20jobs.png)
```

---

## Key Takeaways

This lab helped me understand how Linux commands are used in real DevOps work:

- `&&` chains commands only when the previous command succeeds.
- `|` pipes output from one command into another.
- `>` writes output to a file.
- `>>` appends output to a file.
- `chmod` manages permissions.
- `chown` manages ownership.
- `ps`, `top`, and `kill` help manage processes.
- `curl`, `wget`, `ping`, `dig`, `nslookup`, and `traceroute` help troubleshoot networking.
- `tar`, `gzip`, and `gunzip` help archive and compress files.
- `systemctl` manages services.
- `journalctl` reads system logs.
- `cron` automates scheduled tasks.

## Final Result

Completed a hands-on Linux command-line practice lab covering 50 commands with screenshots, examples, and real-world DevOps use cases.
