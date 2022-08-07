ubah permission file menjadi executeable<br />
<sub> chmod 755 backup_increment.sh </sub><br />
<br />
scheduling dengan cron tiap malam <br />
<sub> crontab -e </sub>  <br />
<sub> 0 0 * * * /bin/sh /$path/backup_increment.sh </sub>
