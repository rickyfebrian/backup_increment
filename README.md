#!/bin/sh
# Backup directory
source=/home/oce/Downloads/increment
dest=/home/oce/backup


for dir in $(find $source -mtime -1 -type d -printf "%P\n") ; do
    if 
    test -d $dest/$dir ; then
    echo "udah ada nih foder $dir dalam folder backup"
    else
    echo "buat dir dulu ya, dir ini >> $dir"
    mkdir -p $dest/$dir
    fi
        for file in $(find $source/$dir -mtime -1 -printf "%P\n") ; do
            if
            test -f $dest/$dir/$file ; then
            echo "udah ada nih file $file di folder $dir, lanjut"
            else
            echo "ada nih file baru, dibuat tanggal $hari_ini >> $file, di dalam dir $dir"
            cp $source/$dir/$file $dest/$dir/
            fi
        done
done


for file2 in $(find $source -type f ! -path "$source/*/*" -mtime -1 -printf "%f\n") ; do
    if
    test -f $dest/$file2 ; then
    echo "lanjut lah, file $file2 udah ada"
    else
    echo "ada nih file baru, dibuat tanggal $hari_ini >> $file2"
    cp $source/$file2 $dest/
    fi
done

