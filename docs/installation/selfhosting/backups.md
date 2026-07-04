# Database Backups

The docker compose stack includes a `db-backup` service that takes a daily `pg_dump` of the `vyhub` database and stores it compressed in the `vyhub-db-backups` Docker volume. Retention:

| Tier | Kept |
|------|------|
| Daily | 7 dumps |
| Weekly | 4 dumps |
| Monthly | 6 dumps |

**List backups:**

``` bash
docker compose exec db-backup ls /backups/last /backups/weekly /backups/monthly
```

**Manually trigger a backup:**

``` bash
docker compose exec db-backup /backup.sh
```

**Restore a backup:**

``` bash
# Pick a file, e.g. /backups/last/vyhub-2024-01-15T020000Z.sql.gz
docker compose exec db-backup \
  sh -c 'zcat /backups/last/<filename>.sql.gz | \
    psql --host=db --username=vyhub --dbname=vyhub'
```

The `vyhub` user password is in `VYHUB_DB_PASSWORD` inside `.env`.
