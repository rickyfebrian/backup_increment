ubah permission file menjadi executeable
chmod 755 backup_increment.sh

scheduling dengan cron tiap malam 
crontab -e
0 0 * * * /bin/sh /$path/backup_increment.sh
