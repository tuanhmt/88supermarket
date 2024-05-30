# How to backup and restore 88supermarket.ca
Date: 2025-05-30
- CPanel url: https://88supermarket.ca:2083
- CPanel account: root88/*****

## 1. Backup
- Login to CPanel -> Search & open Terminal app:
- Change the working directory by command: `cd public_html`
- You must consider renaming the backup file in the backup command below. Here I named the backup file `88supermarket20240530.tar.gz` with `20240325` the current Datetime. It would be best if you changed it by your Datetime you want to:
```sh
drush archive:dump --destination=/home/root88/backup88/88supermarket20240530.tar.gz --tar-options="--exclude=htdgroup.ca --exclude=nailsbyvic-eva.ca --exclude=sophianailsspa.ca --exclude=tiffanynailsbeautysalon.ca --exclude=sites/default/files"
```
- Run your command and wait for a successful
- Check your backup file (with the filename you defined) in the destination folder `/home/root88/backup88`

## 2. Restore
- Login to CPanel -> Search & open Terminal app:
- **Important**: Create a backup
- Change the working directory by command: `cd public_html`
- Run the following restore command and wait (replace the file name by your file):
```sh
drush archive-restore /home/root88/backup88/88supermarket20240530.tar.gz --destination=/home/root88/public_html
```
- Run your command and wait
