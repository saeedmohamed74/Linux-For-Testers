<!-- 🎉 Welcome Banner -->
<p align="center">
  <img src="https://media.giphy.com/media/3o6MblU6k20YkDkU68/giphy.gif" alt="Linux Testing Fun" width="180"/>
</p>

# 🐧 Linux Interview Guide for Software Testers

> _Beautiful, interactive, and beginner-friendly! Unlock Linux skills for your next interview._

---

## 🌟 How to Use This Guide

- Expand the sections below to learn each category.
- Browse clear tables with explanations and examples.
- Practice in your terminal, and shine in your interview!

---

## 📂 File Operations

<details>
<summary>🛠️ <strong>List & Navigate</strong></summary>

**Explanation:**  
File operations are essential to interact with the Linux filesystem. Listing helps you understand what files and directories are present and their properties. Navigation commands move you around the structure, so you can perform actions in the right place.

<table>
<thead>
  <tr>
    <th>Action</th>
    <th>Command</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>List files/folders</td>
    <td><code>ls</code></td>
    <td>Shows files and folders</td>
  </tr>
  <tr>
    <td>Detailed listing</td>
    <td><code>ls -l</code></td>
    <td>Permissions, owner, file size, date</td>
  </tr>
  <tr>
    <td>Show hidden files</td>
    <td><code>ls -a</code></td>
    <td>Include dotfiles</td>
  </tr>
  <tr>
    <td>Human-readable sizes</td>
    <td><code>ls -lh</code></td>
    <td>Display sizes in KB/MB/GB</td>
  </tr>
  <tr>
    <td>Change directory</td>
    <td><code>cd /path/to/dir</code></td>
    <td>Go to a folder</td>
  </tr>
  <tr>
    <td>Home directory</td>
    <td><code>cd ~</code></td>
    <td>Navigate to home</td>
  </tr>
  <tr>
    <td>Up one level</td>
    <td><code>cd ..</code></td>
    <td>Parent directory</td>
  </tr>
  <tr>
    <td>Previous directory</td>
    <td><code>cd -</code></td>
    <td>Switch back</td>
  </tr>
</tbody>
</table>
</details>

<details>
<summary>📁 <strong>Create, Copy & Remove</strong></summary>

**Explanation:**  
Managing files and folders is a daily task for testers. Creating, copying, and deleting ensures you can set up the right environment for tests, back up data, and clean up after experiments.

<table>
<thead>
  <tr>
    <th>Action</th>
    <th>Command</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Create directory</td>
    <td><code>mkdir new_dir</code></td>
    <td>Make a folder</td>
  </tr>
  <tr>
    <td>Nested directories</td>
    <td><code>mkdir -p parent/child</code></td>
    <td>Make parent and child</td>
  </tr>
  <tr>
    <td>Remove empty dir</td>
    <td><code>rmdir empty</code></td>
    <td>Delete empty folder</td>
  </tr>
  <tr>
    <td>Remove dir & contents</td>
    <td><code>rm -r dir</code></td>
    <td>Delete dir & files <b>(Careful!)</b></td>
  </tr>
  <tr>
    <td>Copy file</td>
    <td><code>cp src.txt dest.txt</code></td>
    <td>Duplicate your file</td>
  </tr>
  <tr>
    <td>Copy directory</td>
    <td><code>cp -r src_dir dest_dir</code></td>
    <td>Clone whole folder</td>
  </tr>
  <tr>
    <td>Rename/move</td>
    <td><code>mv old new</code></td>
    <td>Rename or move files</td>
  </tr>
</tbody>
</table>
<strong>Testing Scenario:</strong>  
Suppose you need to back up configuration before a destructive test. Use `cp config.yaml config.yaml.bak` before running the test, and restore with `mv config.yaml.bak config.yaml` if needed.

</details>

---

## 🔍 Text Processing

<details>
<summary>🔎 <strong>Searching & Editing Text</strong></summary>

**Explanation:**  
Testers frequently search logs or data files for errors, warnings, or special patterns. Utilities like grep, sed, and awk are invaluable for analyzing outputs, extracting values, or batch-editing test artifacts.

<table>
<thead>
  <tr>
    <th>Action</th>
    <th>Command</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Find text in file</td>
    <td><code>grep 'error' file</code></td>
    <td>Find "error" lines</td>
  </tr>
  <tr>
    <td>Ignore case</td>
    <td><code>grep -i 'error' file</code></td>
    <td>Match regardless of case</td>
  </tr>
  <tr>
    <td>Recursive grep</td>
    <td><code>grep -r 'TODO' .</code></td>
    <td>Find in all files</td>
  </tr>
  <tr>
    <td>Line numbers</td>
    <td><code>grep -n 'warn' file</code></td>
    <td>Show matches with line number</td>
  </tr>
  <tr>
    <td>Replace text</td>
    <td><code>sed 's/foo/bar/g' file</code></td>
    <td>Swap all "foo" for "bar"</td>
  </tr>
  <tr>
    <td>Delete lines</td>
    <td><code>sed '/DELETE/d' file</code></td>
    <td>Remove unwanted entries</td>
  </tr>
  <tr>
    <td>Print column (awk)</td>
    <td><code>awk '{print $1}' file</code></td>
    <td>Show first column</td>
  </tr>
  <tr>
    <td>Sum values (awk)</td>
    <td><code>awk '{sum+=$2}END{print sum}' file</code></td>
    <td>Add up values from column 2</td>
  </tr>
</tbody>
</table>
<strong>Testing Scenario:</strong>  
Use `grep 'FAIL' test.log` after a test run to quickly detect any failures. Automate analysis with `awk` to count how many tests passed or failed.

</details>

---

## ⚙️ Process Management

<details>
<summary>🖥️ <strong>View & Manage Processes</strong></summary>

**Explanation:**  
Managing processes helps you monitor how your tests run, spot resource hogs, and kill stuck processes. These tasks are routine for testers, especially when running automation or performance tests.

<table>
<thead>
  <tr>
    <th>Action</th>
    <th>Command</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>List your processes</td>
    <td><code>ps</code></td>
    <td>Current user's running processes</td>
  </tr>
  <tr>
    <td>List all processes</td>
    <td><code>ps aux</code></td>
    <td>Complete system process list</td>
  </tr>
  <tr>
    <td>Live monitoring</td>
    <td><code>top</code></td>
    <td>Real-time CPU/RAM view</td>
  </tr>
  <tr>
    <td>Enhanced monitoring</td>
    <td><code>htop</code></td>
    <td>Colorful, interactive UI</td>
  </tr>
  <tr>
    <td>Kill by PID</td>
    <td><code>kill 1234</code></td>
    <td>Gracefully stop process 1234</td>
  </tr>
  <tr>
    <td>Force kill</td>
    <td><code>kill -9 1234</code></td>
    <td>Force stop process 1234</td>
  </tr>
  <tr>
    <td>Kill by name</td>
    <td><code>killall firefox</code></td>
    <td>Stop all named processes</td>
  </tr>
</tbody>
</table>
<strong>Testing Scenario:</strong>  
You run a test and it hangs. Use `ps aux | grep python` to locate the Python test runner and `kill <PID>` to end it, freeing up resources for further runs.

</details>

---

## 🔐 File Permissions

<details>
<summary>🔑 <strong>Permissions & Ownership</strong></summary>

**Explanation:**  
Permissions control who can read, write, or execute files. For testers, setting correct permissions on scripts, logs, and temp files ensures smooth automation and security of sensitive test data.

<table>
<thead>
  <tr>
    <th>Action</th>
    <th>Command</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Show permissions</td>
    <td><code>ls -l file.txt</code></td>
    <td>View permissions, owner info</td>
  </tr>
  <tr>
    <td>Set rwxr-xr-x</td>
    <td><code>chmod 755 script.sh</code></td>
    <td>Owner: all, Group/Other: read+exec</td>
  </tr>
  <tr>
    <td>Set rw-r--r--</td>
    <td><code>chmod 644 doc.txt</code></td>
    <td>Owner: rw, Others: r</td>
  </tr>
  <tr>
    <td>Add execute</td>
    <td><code>chmod +x file</code></td>
    <td>Makes file runnable</td>
  </tr>
  <tr>
    <td>Change owner/group</td>
    <td><code>chown user:group file</code></td>
    <td>Set file owner and group</td>
  </tr>
</tbody>
</table>
<strong>Testing Scenario:</strong>  
Before running a test script, set executable permission via `chmod +x test_script.sh`. After generating logs, restrict access using `chmod 600 sensitive.log`.

</details>

---

## 📊 System Monitoring

<details>
<summary>📈 <strong>Disk, Memory & Uptime</strong></summary>

**Explanation:**  
System monitoring reveals disk usage and memory health. Testers check for enough space and available RAM before running large test suites to avoid failures.

<table>
<thead>
  <tr>
    <th>Action</th>
    <th>Command</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Disk usage</td>
    <td><code>df -h</code></td>
    <td>Show available storage</td>
  </tr>
  <tr>
    <td>Current folder size</td>
    <td><code>du -sh .</code></td>
    <td>Size summary for folder</td>
  </tr>
  <tr>
    <td>RAM/swap</td>
    <td><code>free -h</code></td>
    <td>Total/free memory</td>
  </tr>
  <tr>
    <td>System uptime</td>
    <td><code>uptime</code></td>
    <td>How long Linux has run</td>
  </tr>
  <tr>
    <td>Active user</td>
    <td><code>whoami</code></td>
    <td>Logged in username</td>
  </tr>
</tbody>
</table>
<strong>Testing Scenario:</strong>  
Before a database migration test, use `df -h` to confirm enough disk space and `free -h` to ensure enough memory.

</details>

---

## 🌐 Network Commands

<details>
<summary>🔗 <strong>Connectivity & Download</strong></summary>

**Explanation:**  
Testing often requires fetching files, checking connections, and troubleshooting access to remote services. These commands help you ensure your environment can reach required endpoints.

<table>
<thead>
  <tr>
    <th>Action</th>
    <th>Command</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Ping test</td>
    <td><code>ping google.com</code></td>
    <td>Check connectivity</td>
  </tr>
  <tr>
    <td>Network info</td>
    <td><code>ip a</code></td>
    <td>Show interfaces/addresses</td>
  </tr>
  <tr>
    <td>Listening ports</td>
    <td><code>netstat -tuln</code></td>
    <td>Which services are open</td>
  </tr>
  <tr>
    <td>Download file (wget)</td>
    <td><code>wget http://site.com/file</code></td>
    <td>Fetch file</td>
  </tr>
  <tr>
    <td>Download file (curl)</td>
    <td><code>curl -O http://site.com/file</code></td>
    <td>Save file with curl</td>
  </tr>
</tbody>
</table>
<strong>Testing Scenario:</strong>  
Run `ping testserver.local` before API automation to ensure the server is up. Use `wget`/`curl` to pull new test datasets.

</details>

---

## 📝 Log Analysis

<details>
<summary>📜 <strong>Monitor & Search Logs</strong></summary>

**Explanation:**  
Log analysis is crucial in testing to catch errors, review process flow, and investigate failures. Mastering log tools lets you diagnose issues faster.

<table>
<thead>
  <tr>
    <th>Action</th>
    <th>Command</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Follow log</td>
    <td><code>tail -f /var/log/syslog</code></td>
    <td>Live updates to syslog</td>
  </tr>
  <tr>
    <td>Search for errors</td>
    <td><code>grep 'error' /var/log/syslog</code></td>
    <td>Find error entries</td>
  </tr>
  <tr>
    <td>View start of log</td>
    <td><code>head -n 20 /var/log/app.log</code></td>
    <td>First 20 log lines</td>
  </tr>
</tbody>
</table>
<strong>Testing Scenario:</strong>  
After running functional tests, use `grep 'FAILED' results.log` to list failed cases instantly for bug reporting, and `tail -f` on system logs to watch for crashes in real time.

</details>

---

## 💡 Interview/Test Scenarios

<details>
<summary>🛠️ <strong>Testing Troubleshooting Examples</strong></summary>

<table>
<thead>
  <tr>
    <th>Scenario</th>
    <th>Commands & Steps</th>
    <th>How it Helps</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Find disk hogs before test</td>
    <td>
      <code>df -h</code><br>
      <code>du -sh * | sort -h | tail -n 5</code>
    </td>
    <td>Spot which directories eat space, avoid test failures</td>
  </tr>
  <tr>
    <td>Stop runaway test processes</td>
    <td>
      <code>ps aux --sort=-%cpu | head -n 5</code><br>
      <code>kill &lt;PID&gt;</code>
    </td>
    <td>Shut down tests that consume too many resources</td>
  </tr>
  <tr>
    <td>Error diagnosis after run</td>
    <td>
      <code>tail -f /var/log/app.log | grep 'ERROR'</code>
    </td>
    <td>Monitor log in real-time for failed assertions</td>
  </tr>
  <tr>
    <td>Permission troubleshooting</td>
    <td>
      <code>ls -l /test/data</code><br>
      <code>chmod 644 /test/data/results.txt</code>
    </td>
    <td>Fix "Permission Denied" issues while saving results</td>
  </tr>
  <tr>
    <td>Network connectivity check</td>
    <td>
      <code>ping api.example.com</code><br>
      <code>curl -I http://api.example.com</code>
    </td>
    <td>Verify service is reachable before integration tests</td>
  </tr>
</tbody>
</table>

**Bonus Interview Question Ideas:**
- How would you investigate missing test results after a run?
- What steps would you take to automate cleanup of temporary files post-test?
- How do you ensure scripts are run with correct user permissions and environment variables?
</details>

---

<p align="center"><b>😊 Good luck on your interview! Practice, explore, and enjoy Linux!</b> 🚀</p>
