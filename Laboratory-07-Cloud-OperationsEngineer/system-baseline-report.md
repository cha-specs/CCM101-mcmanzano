
# System Baseline Report

## 1. Introduction
This report documents the initial health and resource capacity of the host server before deploying the Nginx web server. The monitoring was performed using Linux command-line tools in the KillerCoda Ubuntu Playground.

## 2. Monitoring Commands

### Memory Usage
Command executed:

```bash
free -h
```

**Total RAM:** [Enter the total RAM shown in your terminal]

**Available RAM:** [Enter the available RAM shown in your terminal]

**Screenshot:** `screenshots/memory-check.png`

### Disk Storage
Command executed:

```bash
df -h /
```

**Root File System Capacity:** [Enter the total size shown under the Size column]

**Used Storage:** [Enter the value shown under the Used column]

**Available Storage:** [Enter the value shown under the Avail column]

**Screenshot:** `screenshots/disk-check.png`

### CPU Load and Running Processes
Command executed:

```bash
top
```

The `top` command displays active processes, CPU utilization, memory usage, and system load in real time.

## 3. Importance of Disk Space Monitoring
Checking disk space before a massive traffic surge is important because insufficient storage can prevent the server from saving logs, temporary files, and application data, potentially causing errors or service interruptions.

## 4. Conclusion
The host server's memory and disk capacity were checked before deploying the web application. These baseline measurements provide an initial reference for identifying possible resource problems during application monitoring.

