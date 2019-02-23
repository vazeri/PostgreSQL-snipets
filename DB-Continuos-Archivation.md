https://www.zimmi.cz/posts/2018/postgresql-backup-and-recovery-orchestration-wal-archiving/

Ubuntu 18.04

 ### Find postgresql.conf

psql -U postgres -c 'SHOW config_file'

 ### Configure postgres.conf 

nano /etc/postgresql/10/main/postgresql.conf
```
wal_level = replica
archive_mode = on
archive_command = test ! -f /backup/wal/%f && cp %p /backup/wal/%f
```
 ### 
 
