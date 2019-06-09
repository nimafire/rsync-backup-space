# rsync-backup-space
this simple bash script will check available space on partition / and then start rsync to update new files into backup storage
<br>
this script is based on :<br>
* Centos7
* Cpanel 11+
<br>(ive check this on centos 5/6/7 and ubuntu and work fine.)<br><br>

<b> Story of this script</b><br>
at midnight ive receive a sms: server X is down!<br><br>
after checking I figure out partition / was full and mysql gets down. it takes 30 min to find the reason..!!<br>
I had added a new HDD to the server (last week) which name is /dev/sdc1 and mount it to /backup, but I haven't added this on fstab to remount when system restart.<br>

after an unwanted restart, /backup revert back into / (not /dev/sdc) and when backup run, it store all data into / instead of new hdd <br>
this script check / space and then try to run an rsync command.
else it will notify admin about usage of /
