# Laboratory 09: Cloud Automation Engineer

## Mission Overview

This laboratory activity focuses on automating cloud administration tasks using Bash shell scripting and Cron scheduling in a Linux environment. The main task is to create a Bash script that automatically compresses application data into a backup file and configure a Cron job to schedule the backup every night at 2:00 AM.

Using the KillerCoda Ubuntu Playground, I practiced creating directories, writing scripts using Nano, modifying file permissions, executing commands, and scheduling automated tasks. This activity demonstrates how automation can reduce manual work, improve consistency, and help protect important data in cloud environments.

## Objectives

- Understand the fundamentals of Bash shell scripting.
- Create and execute a Bash script using the Nano text editor.
- Use variables to make scripts more flexible and reusable.
- Modify file permissions using the `chmod` command.
- Create compressed backups using the `tar` command.
- Configure a Cron job to run a script automatically.
- Document the process and results using Markdown.
- Complete and organize the ninth laboratory activity in the GitHub Cloud Computing Portfolio.

## Commands Executed

The following commands were used during the laboratory activity:

```bash
# Create a directory for application data
mkdir app-data

# Create a sample data file
echo "This is critical client data." > app-data/data.txt

# Create the backup script
nano backup.sh

# Attempt to execute the script
./backup.sh

# Grant executable permission
chmod +x backup.sh

# Execute the backup script
./backup.sh

# Display the generated backup files
ls -l backups/

# Display existing Cron jobs
crontab -l

# Edit the Cron configuration
env EDITOR=nano crontab -e

# Verify the installed Cron schedule
crontab -l
```

## Skills Learned

- **Bash Scripting:** Writing commands in a script to automate repetitive tasks.
- **Linux File Management:** Creating directories and files through the terminal.
- **File Permissions:** Using `chmod +x` to allow a script to execute.
- **Data Backup:** Compressing application data into `.tar.gz` archives.
- **Task Scheduling:** Configuring Cron to run commands automatically.
- **Technical Documentation:** Writing clear instructions and explanations using Markdown.
- **GitHub Portfolio Management:** Organizing laboratory files and preparing evidence of completed tasks.

## Expected Output

After running the backup script, a `backups/` directory should contain a compressed backup file with a timestamp in its filename, such as:

```text
backups/
└── backup_20261015_020000.tar.gz
```

The actual filename depends on the date and time when the script is executed.

The Cron configuration should contain the following schedule:

```cron
0 2 * * * /root/backup.sh
```

This configuration schedules the script to run every day at 2:00 AM, provided that the script exists at the specified path and the Cron service is running.

## Screenshots

The `screenshots/` folder contains evidence of the completed laboratory tasks.

- `script-execution.png` — Shows the backup script execution and the generated compressed backup file.
- `cron-schedule.png` — Shows the installed Cron schedule using the `crontab -l` command.

## Conclusion

This laboratory activity helped me understand how Bash scripting and Cron scheduling can automate repetitive administrative tasks. I learned that automation is useful for improving efficiency and consistency, especially when managing cloud resources. I also realized that scripts and scheduled tasks must be tested carefully to prevent errors and protect important data.
