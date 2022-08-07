ubah permission file menjadi executeable<br />
chmod 755 backup_increment.sh <br />
<br />
scheduling dengan cron tiap malam <br />
crontab -e <br />
0 0 * * * /bin/sh /$path/backup_increment.sh
