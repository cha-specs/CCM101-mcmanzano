
# Backup Script Guide

## 1. Overview

The `backup.sh` script automates the process of backing up the `app-data` directory. It creates a backup directory, generates a timestamp, and compresses the application data into a `.tar.gz` file.

## 2. Complete Bash Script

```bash
#!/bin/bash
# Automated Backup Script for CloudNova Technologies

SOURCE_DIR="app-data"
BACKUP_DIR="backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Initiating automated backup..."

# Create the backup directory if it does not exist
mkdir -p "$BACKUP_DIR"

# Compress the source directory into a tarball (.tar.gz)
tar -czf "$BACKUP_DIR/backup_$TIMESTAMP.tar.gz" "$SOURCE_DIR"

echo "Backup completed successfully at $TIMESTAMP!"
```

## 3. Explanation of the Script

- `#!/bin/bash` specifies Bash as the script interpreter.
- `SOURCE_DIR="app-data"` defines the directory to back up.
- `BACKUP_DIR="backups"` defines where the backup files will be stored.
- `TIMESTAMP=$(date +"%Y%m%d_%H%M%S")` generates a timestamp for the backup filename.
- `echo` displays messages in the terminal.
- `mkdir -p "$BACKUP_DIR"` creates the backup directory if it does not exist.
- `tar -czf` creates a compressed archive of the source directory.
- `"$BACKUP_DIR/backup_$TIMESTAMP.tar.gz"` defines the output filename.

## 4. File Permissions

The command below grants execute permission to the script:

```bash
chmod +x backup.sh
```

The `chmod` command changes file permissions, while `+x` adds permission to execute the file. After this command, the script can be run using `./backup.sh`, provided the user has the necessary permissions.

## 5. Testing the Script

Run the script using:

```bash
./backup.sh
```

Check the generated backup file using:

```bash
ls -l backups/
```

The backup directory should contain a compressed `.tar.gz` file with a timestamp in its filename.

## 6. Cron Job Configuration

The Cron expression used for scheduling is:

```cron
0 2 * * * /root/backup.sh
```

This configuration schedules the script to run every day at 2:00 AM, provided the Cron service is running and the script is accessible at the specified path.

### Cron Field Breakdown

| Field | Value | Meaning |
|---|---|---|
| Minute | `0` | Runs at minute zero. |
| Hour | `2` | Runs at 2:00 AM. |
| Day of Month | `*` | Runs every day of the month. |
| Month | `*` | Runs every month. |
| Day of Week | `*` | Runs every day of the week. |

### Installing the Cron Job

Open the Cron editor:

```bash
env EDITOR=nano crontab -e
```

Add the following line:

```cron
0 2 * * * /root/backup.sh
```

Save the file, then verify the schedule:

```bash
crontab -l
```

**Important:** The path `/root/backup.sh` works only if the script is actually located there and the Cron job runs under the appropriate account. If your script is stored elsewhere, use its actual absolute path.

## 7. Conclusion

This activity demonstrates how Bash scripting, file permissions, and Cron scheduling can automate routine cloud administration tasks. Automated backups reduce repetitive manual work and help maintain copies of important application data.
