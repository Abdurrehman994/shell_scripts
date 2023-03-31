```# shell_scripts
---------backup_file---------------
defining bash folder
#!/bin/bash  

defining source and destination folders and saving it into a variable
src_dir=/home/rehman/scripts
tgt_dir=/home/rehman/backups

creating timestamp
curr_timestamp=$(date  "+%Y-%m-%d-%H-%M-%S")

naming file name
backup_file=$tgt_dir/$curr_timestamp.tgz

printing variables
echo "$curr_timestamp"
echo " $backup_file"

creating zip file
tar czf $backup_file --absolute-names $src_dir
echo "backup complete"

------------------------check disk usage---------------
#!/bin/bash
df--command to check disk usage
awk command used to for text processing
df -H | awk  '{print $5 " " $1}' | while read output;
 
printing usage values by removing the '%' symbol
do
 usage=$(echo $output | awk '{print $1}' | cut -d'%' -f1)
 echo $usage
done
cronjob command 
shell script is running complete 12th hour result will appending in check_disk.txt file
* 12 * * * bash /home/ubuntu/check_disk.sh >> /home/ubuntu/check_disk.txt
```
