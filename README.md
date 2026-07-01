# Python Log Analyzer

A Python-based cybersecurity tool that analyzes Linux authentication logs to detect failed login attempts, identify suspicious IP addresses, and generate security reports.

## Project Overview

This project demonstrates how Python can be used to automate security log analysis. It parses Linux authentication logs (`auth.log`), extracts failed SSH login attempts, counts failed logins by IP address, flags suspicious activity, and generates a report.

This project is designed to showcase skills relevant to SOC Analyst, Cybersecurity Analyst, and Security Engineer roles.

---

## Features

- Reads Linux authentication logs
- Detects failed SSH login attempts
- Extracts source IP addresses using Regular Expressions (Regex)
- Counts failed login attempts by IP
- Flags suspicious IP addresses
- Generates a security report
- Easy to customize for different environments

---

## Technologies Used

- Python 3
- Regular Expressions (re)
- Collections (Counter)
- File Handling
- Linux Authentication Logs
- Cybersecurity Log Analysis

---

## Project Structure

```
python-log-analyzer/
│
├── logs/
│   └── auth.log
│
├── analyzer.py
├── requirements.txt
├── README.md
└── screenshots/
```

---

## Sample Log Entry

```
Jul 12 10:15:01 server sshd[2345]: Failed password for invalid user admin from 192.168.1.10 port 55321 ssh2
```

---

## How It Works

1. Opens the authentication log file.
2. Searches for failed SSH login attempts.
3. Extracts the IP address using Regex.
4. Counts failed login attempts for each IP.
5. Flags IPs exceeding a configurable threshold.
6. Generates a security report.

---

## Installation

Clone the repository.

```bash
git clone https://github.com/Abdifatah206/User_log_analysis/tree/main
```
---

## Usage

Run the analyzer.

```bash
python analyzer.py
```

---
## Code

```
import re
from collections import Counter
log_file = "auth.log"
failed_pattern = r"Failed password.*from (\d+\.\d+\.\d+\.\d+)"
failed_ips = []

with open(log_file, "r") as file:
    for line in file:
        match = re.search(failed_pattern, line)
        if match:
            failed_ips.append(match.group(1))
counter = Counter(failed_ips)
print("=" * 40)
print("failed log analysis")
print("=" * 40)
for ip, count in counter.items():
    print(f"{ip} -> {count} failed attempts")
```

## Example Output

```
========================================
 Failed Login Analysis
========================================

192.168.1.10 -> 3 failed attempts

203.0.113.50 -> 1 failed attempts


```


## Skills Demonstrated

- Python Programming
- Cybersecurity
- Log Analysis
- Linux Security
- SSH Authentication Monitoring
- Regular Expressions (Regex)
- Threat Detection
- Incident Reporting
- Automation
- File Processing

---

## Learning Objectives

This project demonstrates practical cybersecurity skills by combining Python programming with security log analysis. It provides experience in parsing logs, identifying suspicious activity, and automating incident reporting.

---

## Author

**Abdifatah Shire Mohamed**

Cybersecurity | Python | Cloud Security | Security+

GitHub: https://github.com/yourusername

LinkedIn: https://linkedin.com/in/yourprofile
