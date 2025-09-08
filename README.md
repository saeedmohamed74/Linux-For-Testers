The Indispensable Linux Command Line Handbook for the Aspiring Software Tester
<p align="center">
<img src="https://www.google.com/search?q=https://placehold.co/600x200/2d3748/ffffff%3Ftext%3DLinux%2Bfor%2BTesters%26font%3Draleway" alt="Linux for Testers Banner"/>
</p>

<p align="center">
<img src="https://www.google.com/search?q=https://img.shields.io/badge/License-MIT-blue.svg" alt="License: MIT">
<img src="https://www.google.com/search?q=https://img.shields.io/github/last-commit/saeedmohamed74/Linux-For-Testers" alt="last commit">
<img src="https://www.google.com/search?q=https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs Welcome">
</p>

A comprehensive guide and a collection of utility scripts designed for junior software testers preparing for interviews that include Linux-based questions.

📋 Table of Contents
Mastering the Linux Environment

The Essential Command Toolkit

The Interview Gauntlet

Leveling Up with Shell Scripting

How to Use the Scripts

Mastering the Linux Environment: Core Concepts for Testers
For a software tester, proficiency in Linux is not merely an auxiliary skill; it is a fundamental competency. The command line interface (CLI) serves as the primary diagnostic and investigative tool, offering direct, unfiltered access to the environment where applications are deployed, executed, and, critically, where they fail.

Navigating the Filesystem with Purpose: A Tester's Guided Tour
A software tester's focus is targeted on the application and its immediate environment.

/var/log: The primary source for diagnostic information.

/tmp & /var/tmp: Locations for temporary application files.

/etc: Central location for system-wide configuration files.

/home/user: Your personal workspace for test scripts and data.

Application-specific directories: e.g., /opt/myapp

The Language of Permissions: Your Key to the System
File permissions are a frequent source of test failures. A common bug is an application failing to write to its log. Your first check would be ls -l /var/log/app.log to see if the user running the application has write (w) permissions on the file.

<details>
<summary><strong>Click to Expand: File Permissions Chart (rwx)</strong></summary>

Octal Value

Binary Representation

Permissions (rwx)

Description

0

000

---

No permissions

1

001

--x

Execute only

2

010

-w-

Write only

3

011

-wx

Write and execute

4

100

r--

Read only

5

101

r-x

Read and execute

6

110

rw-

Read and write

7

111

rwx

Read, write, and execute

</details>

The Essential Command Toolkit: A Tester's Daily Arsenal
The real power comes from composing these commands with pipes (|) and redirection (>).

<details>
<summary><strong>Click to Expand: Essential Commands Table</strong></summary>

Command

Common Usage

QA Use Case

ls

ls -lath

List all files with details, human-readable sizes, sorted by most recently modified.

grep

grep -i -C 3 "error" app.log

Search for "error" (case-insensitive) in app.log and show 3 lines of context around each match.

tail

tail -f /var/log/messages

Watch a system log file in real-time to see new entries as they are written.

find

find . -name "*.xml"

Find all files with the .xml extension in the current directory and its subdirectories.

ps

ps aux | grep "java"

List all running processes and filter the list to show only those related to "java".

top

top (then press 'P' or 'M')

Get a real-time view of system processes, sorted by CPU or Memory usage to identify resource hogs.

df

df -h

Quickly check the available disk space on all mounted partitions to prevent test failures.

du

du -sh /data/logs

Check the total size of a specific log directory to see if it needs cleaning up.

ss

ss -tuln | grep 8080

Check if any process is listening on TCP port 8080, verifying a web server has started correctly.

curl

curl http://localhost:8080/health

Perform a basic health check on a local web service to see if it's responding.

kill

kill -15 12345

Send a graceful shutdown signal (SIGTERM). Use kill -9 (SIGKILL) as a last resort.

tar

tar -czvf results.tar.gz ./results

Create a compressed archive of the results directory for sharing or backup.

</details>

The Interview Gauntlet: Real-World Scenarios and Solutions
Interview questions focus on your problem-solving workflow. Articulate your thought process clearly.

Scenario: Application is running, but you can't access it from the browser.

Verify the process is listening: ss -tuln | grep <port_number>

Check for firewall rules: sudo iptables -L

Check application logs for network errors: tail -n 100 /var/log/app.log

Scenario: The application has crashed.

Check system logs for out-of-memory errors: grep -i "out of memory" /var/log/messages

Locate a core dump file: find / -name "core*"

Check available disk space: df -h

Leveling Up: An Introduction to Shell Scripting for QA Automation
Showing that you can automate repetitive tasks is a huge plus. The example scripts for common QA tasks are located in the /scripts directory.

health_check.sh: Automates a system health check and saves a timestamped report.

scan_log.sh: Scans a log file for a list of predefined error patterns.

backup_test_data.sh: Creates a timestamped backup of a directory.

How to Use the Scripts
Clone the repository:

git clone [https://github.com/saeedmohamed74/Linux-For-Testers.git](https://github.com/saeedmohamed74/Linux-For-Testers.git)
cd Linux-For-Testers

Make them executable: Before you can run the scripts, you need to give them execute permissions.

chmod +x scripts/*.sh

Run a script: For example, to scan a log file:

./scripts/scan_log.sh /var/log/syslog
