```markdown
# TermSyncTools

TermSyncTools is a CLI tool to backup and restore Termux environments. It allows you to easily backup your home directory and installed packages, and restore them when needed. The backups are stored on Google Drive using `rclone`.

## Features

- Backup and restore Termux home directory and installed packages.
- Store backups on Google Drive using `rclone`.
- Automatically synchronize backups with Google Drive.
- User-friendly interface with colorful output.
- Easy to use with simple command-line options.
- Support for multiple cloud services (Google Drive, Dropbox, OneDrive, Amazon S3).
- Automatic scheduling of backups using cron jobs.
- Delete existing backups.
- Unschedule existing cron jobs.

## Installation

1. **Install Dependencies**:
   Ensure you have the following dependencies installed:
   ```sh
   apt-get update && apt-get upgrade -y
   apt-get install -y tar pigz rclone figlet lolcat
   pkg install ruby
   gem install lolcat
   ```

2. **Configure `rclone`**:
   If `rclone` is not configured with Google Drive, you will be prompted to configure it during the first run.

3. **Grant Storage Permission**:
   Ensure Termux has storage permission:
   ```sh
   termux-setup-storage
   ```

## Usage

### Backup

To backup your home directory and installed packages, use the `-b` option:
```sh
TermSyncTools -b [home|pkgs]
```
You will be prompted to enter a name for the backup. If no name is provided, a default name with the current date and time will be used.

### Restore

To restore your home directory and installed packages, use the `-r` option:
```sh
TermSyncTools -r [home|pkgs]
```
You will be presented with a list of available backups to choose from.

### Sync with Cloud Service

To synchronize backups with a cloud service, use the `-s` option:
```sh
TermSyncTools -s [google|dropbox|onedrive|s3]
```

### Schedule Cron Jobs

To configure automatic backups using cron jobs, use the `-c` option:
```sh
TermSyncTools -c
```

### Delete Backups

To delete existing backups, use the `-d` option:
```sh
TermSyncTools -d
```

### Unschedule Cron Jobs

To unschedule existing cron jobs, use the `-u` option:
```sh
TermSyncTools -u
```

### Help

To display the help message, use the `-h` option:
```sh
TermSyncTools -h
```

### Version

To display the version of TermSyncTools, use the `-v` option:
```sh
TermSyncTools -v
```

## Example

### Backup Example
```sh
TermSyncTools -b home
```
Output:
```
Backing up home
    Be patient...

[ ✓ ] home backed up and can be found in
    /data/data/com.termux/files/home/storage/shared/Termux/Backup/my_backup_home.bak
```

### Restore Example
```sh
TermSyncTools -r home
```
Output:
```
Available home backups:
    1. /data/data/com.termux/files/home/storage/shared/Termux/Backup/my_backup_home.bak
Enter the number of the backup to restore: 1
Restoring home
    Be patient...

[ ✓ ] home restored
    start a new session.
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## Acknowledgments

- Thanks to the Termux community for their support and contributions.
- Special thanks to [tuxgyver](https://github.com/tuxgyver/TermSyncTools) for the original script even if it was me who gave him the ideas and features of this project because we launched it together.

## Contact

[arkoreal2021@gmail.com](https://mail.google.com/mail/u/0/#inbox?compose=CllgCJNxNNDgCTWlhGsVWTMjCfRxzMkdXGtctbNTtLhdmSxhLzqCLdJjBlMzVCWvtGDqPpXZBsq)

For any questions or issues, please open an issue on the GitHub repository.
```

Vous pouvez copier ce contenu dans un fichier nommé `README.md` dans le répertoire racine de votre projet sur GitHub. Cela fournira une documentation claire et utile pour les utilisateurs de votre outil `TermSyncTools`.
