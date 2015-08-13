# Backup and Restore

## Backup

### Manual backup

Backups are triggered directly via the Web Interface or via the CLI. The backup
creates a complete snapshot of the environment. It includes all
persistent data from all running services (MySQL, SOLR...) and any files
stored on the mounted volumes.

> **note**
> Make backups of your live environment before merging an environment to the live environment.

Using the CLI:

```bash
$ platform environment:backup
```

### Automated backups

**Platform.sh Standard**

No backup is triggered automatically on Platform.sh Standard. You can
trigger your backup via the Web Interface or via the CLI.

If you want to automate your backups, you can use Jenkins and trigger
the following CLI command:

```bash
$ platform environment:backup
```

> **note**
> We advise you to backup your environment each time you increase the storage space of your services.

> **note**
> The snapshots are currently retained indefinitely. However, we don't recommend depending on them for more than 1 week. If we begin purging snapshots at any time, we'll notify customers.

**Platform.sh Enterprise**

Platform.sh Enterprise backups are run daily. Backups are retained for a
month.

In parallel we run EBS snapshots every four hours. Those snapshots are
kept for seven days.

## Restore

Commerce Guys can restore from backup for you. Request a restore by
opening a ticket which contains the name of the environment to restore.
