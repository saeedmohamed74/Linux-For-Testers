<div align="center">

<img src="https://www.google.com/search?q=https://placehold.co/1200x300/1a202c/9f7aea%3Ftext%3DLinux%2Bfor%2BTesters%26font%3Draleway" alt="Linux for Testers Banner"/>

The Indispensable Linux Handbook for the Aspiring Software Tester
A comprehensive guide and collection of utility scripts designed for junior software testers preparing for interviews that include Linux-based questions.

<p>
<a href="https://www.google.com/search?q=https://github.com/saeedmohamed74/Linux-For-Testers/stargazers"><img src="https://www.google.com/search?q=https://img.shields.io/github/stars/saeedmohamed74/Linux-For-Testers%3Fstyle%3Dfor-the-badge%26color%3D805AD5%26logo%3Dgithub" alt="Stars"></a>
<a href="https://www.google.com/search?q=https://github.com/saeedmohamed74/Linux-For-Testers/network/members"><img src="https://www.google.com/search?q=https://img.shields.io/github/forks/saeedmohamed74/Linux-For-Testers%3Fstyle%3Dfor-the-badge%26color%3D805AD5%26logo%3Dgithub" alt="Forks"></a>
<img src="https://www.google.com/search?q=https://img.shields.io/github/last-commit/saeedmohamed74/Linux-For-Testers%3Fstyle%3Dfor-the-badge%26color%3D805AD5%26logo%3Dgithub" alt="last commit">
<img src="https://www.google.com/search?q=https://img.shields.io/badge/License-MIT-blue.svg%3Fstyle%3Dfor-the-badge%26color%3D805AD5" alt="License: MIT">
</p>
</div>

✨ Key Features
<table width="100%">
<tr>
<td width="25%" align="center" style="padding: 15px;">
<img src="https://www.google.com/search?q=https://placehold.co/80x80/2d3748/ffffff%3Ftext%3D🚀&font=lato" alt="Core Concepts Icon" style="border-radius: 50%;">
<br><strong>Core Concepts</strong>
<p style="font-size: smaller;">Master the filesystem, permissions, and the shell.</p>
</td>
<td width="25%" align="center" style="padding: 15px;">
<img src="https://www.google.com/search?q=https://placehold.co/80x80/2d3748/ffffff%3Ftext%3D🛠️&font=lato" alt="Toolkit Icon" style="border-radius: 50%;">
<br><strong>Essential Toolkit</strong>
<p style="font-size: smaller;">A deep dive into the commands you'll use every day.</p>
</td>
<td width="25%" align="center" style="padding: 15px;">
<img src="https://www.google.com/search?q=https://placehold.co/80x80/2d3748/ffffff%3Ftext%3D💡&font=lato" alt="Scenarios Icon" style="border-radius: 50%;">
<br><strong>Interview Scenarios</strong>
<p style="font-size: smaller;">Tackle real-world problems and impress your interviewer.</p>
</td>
<td width="25%" align="center" style="padding: 15px;">
<img src="https://www.google.com/search?q=https://placehold.co/80x80/2d3748/ffffff%3Ftext%3D🤖&font=lato" alt="Automation Icon" style="border-radius: 50%;">
<br><strong>QA Automation</strong>
<p style="font-size: smaller;">Useful shell scripts to automate repetitive tasks.</p>
</td>
</tr>
</table>

🚀 Mastering the Linux Environment
The command line is the primary diagnostic and investigative tool for a software tester. It offers direct, unfiltered access to the application environment.

🗺️ Navigating the Filesystem: Key directories include /var/log, /tmp, /etc, and /home/user.

🔑 The Language of Permissions: A frequent source of bugs! Use ls -l to view permissions and chmod to change them.

🛠️ The Essential Command Toolkit
<details>
<summary><strong>Click to expand the Essential Commands Table</strong></summary>
<br>

Command

QA Use Case

ls

ls -lath - List all files with details, sorted by most recently modified.

grep

grep -i -C 3 "error" app.log - Search for "error" and show 3 lines of context.

tail

tail -f /var/log/messages - Watch a log file in real-time.

find

find . -name "*.xml" - Find all XML files in the current directory.

ps

ps aux | grep "java" - List all running processes and filter for "java".

top

top (then press 'P' or 'M') - View processes sorted by CPU or Memory.

df

df -h - Quickly check available disk space.

curl

curl http://localhost:8080/health - Perform a basic health check on a web service.

kill

kill -15 12345 - Send a graceful shutdown signal. Use kill -9 as a last resort.

tar

tar -czvf results.tar.gz ./results - Create a compressed archive of a directory.

</details>

💡 The Interview Gauntlet: Real-World Scenarios
Here's how to approach common interview problems:

Scenario: Application is running, but you can't access it from the browser.
# 1. Is the process listening on the correct port?
ss -tuln | grep <port_number>

# 2. Is a firewall blocking the port?
sudo iptables -L

# 3. Are there network-related errors in the logs?
tail -n 100 /var/log/app.log

Scenario: The application has crashed.
# 1. Any out-of-memory errors in system logs?
grep -i "out of memory" /var/log/messages

# 2. Can you find a core dump file?
find / -name "core*"

# 3. Is the disk full?
df -h

🤖 Leveling Up with Shell Scripting
The example scripts for automating common QA tasks are in the /scripts directory.

health_check.sh: Automates a system health check.

scan_log.sh: Scans a log file for predefined error patterns.

backup_test_data.sh: Creates a timestamped backup of a directory.

🏃 How to Run the Scripts
Make the scripts executable (only need to do this once):

chmod +x scripts/*.sh

Execute a script:

# Example: Scan the system log for errors
./scripts/scan_log.sh /var/log/syslog
