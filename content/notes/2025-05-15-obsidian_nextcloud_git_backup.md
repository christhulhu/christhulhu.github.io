---
title: "Backup-Strategy: Obsidian Notes to Git with NextCloud"
date: 2025-05-15
tags:
- backup-strategy
- git
- home-it
- home-automation
- self-hosting
---
There are plugins that add functionality to Obsidian to automatically backup your notes in a Git server or even use IT for synchronization between multiple devices.

Personally, I use my NextCloud instance and the `Remotely Save` Plugin for sync. But I want to be better safe than sorry and I know about the advantages of file revisions/versions provided by Git SCM. For this reason I wanted to backup my notes regularily in my Gitea instance on my [vps](/vps). Unfortunately, the Git Plugin for Obsidian is experimental for mobile devices. So I needed a different approach...

On my [home server](/home-it) I have a continous sync with my NextCloud using `nextcloudcmd` as headless client and a simple `cron` job.
Another job Is now responsible to commit a snapshot of my notes once a day into the remote Git Repository.

![Backup Sequence diagram](/images/obsidian_nextcloud_git_backup.png)

## Setup NextCloud Sync

I use Rocky Linux on my home server and installed the `nextcloud-client` with `dnf`

```bash
sudo dnf install nextcloud-client
```

  
Afterwards, I created a wrapper script in `~/bin/nextcloud-sync.sh` that gets called by a `cron` job to sync from my remote server to my local server:

```bash
#!/bin/bash

nextcloudcmd ~/nextcloud https://user:password@server.tld
```

(Of course the local directory `~/nextcloud` should be present on the server.

## Initialize Git Repository

**Assumption**: You already have `git` installed on the Server.

```bash
cd ~/nextcloud/notes
git init
git remote add origin git@git-server:username/repo.git
```

### Setup Credential Helper

```bash
git config --global credential.helper store
```

### Optional: Setup `.gitignore`

If you want to exclude some files (or pattern) from your Git repo, you need to create a `.gitignore` file.

### Manual Initial commit to Store Credential

```bash
git commit -am "initial commit"
git push --set-upstream origin main
```

This step should query you for your Git credentials that are stored in the Git Credential Helper afterwards and will be reused by our `cronjob`.

## Backup Script for periodic backups

```bash
#!/bin/bash

# === Konfiguration ===
REPO_DIR="$HOME/nextcloud/notes"
LOGFILE="$REPO_DIR/git-backup.log"
DATE=$(date '+%Y-%m-%d %H:%M:%S')

# === Logging-Funktion ===
log() {
    echo "[$DATE] $1" >> "$LOGFILE"
}

# === Ausführung ===
cd "$REPO_DIR" || {
    log "FEHLER: Verzeichnis $REPO_DIR nicht gefunden."
    exit 1
}

# === Git Workflow ===
log "Starte Git-Backup..."

# Änderungen erfassen
git add . >> "$LOGFILE" 2>&1

# Nur committen, wenn es auch Änderungen gibt
if ! git diff --cached --quiet; then
    git commit -m "Automatisches Backup: $DATE" >> "$LOGFILE" 2>&1
    git push >> "$LOGFILE" 2>&1

    if [ $? -eq 0 ]; then
        log "Backup erfolgreich gepusht."
    else
        log "FEHLER beim Push."
    fi
else
    log "Keine Änderungen – kein Commit notwendig."
fi
```

## Crontab

Edit the `crontab` with the command

```bash
crontab -e
```
For this backup I added two periodic jobs:

```crontab
*/15 * * * $HOME/bin/nextcloud-sync.sh
0 3 * * * $HOME/bin/obsidian_git_backup.sh
```