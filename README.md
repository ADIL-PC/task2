#!/bin/bash #Creating a bash script for backups
BACKUPTIME=`date +%b-%d-%y` #get the current date
DESTINATION=/root/backup/ #create all backup here in this folder
mkdir $DESTINATION/$BACKUPTIME
find -L /var/log -name "*.gz" -exec cp {} $DESTINATION/$BACKUPTIME/ \; #find *.gz files
cd $DESTINATION
tar cvzf backup-$BACKUPTIME.tar.gz $DESTINATION
rm -R $BACKUPTIME

