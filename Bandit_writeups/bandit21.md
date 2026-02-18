## Bandit Level 20 → 21 - OverTheWire

This guide will help you retrieve the password for Bandit Level 21 by investigating a scheduled task.

## Objective

A program runs periodically using cron. We’ll find out what it does and uncover the next password.

## Steps

1. List the cron job configuration files:

>   la /etc/cron.d
behemoth4_cleanup  cronjob_bandit22  cronjob_bandit24  leviathan5_cleanup    otw-tmp-dir   sysstat
clean_tmp          cronjob_bandit23  e2scrub_all       manpage3_resetpw_job  .placeholder
   ```

   This will show all cron jobs. Look for one related to bandit22—this is the next level we need.

2. Check the content of the relevant cron job file:

>cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null

this file, you’ll find the command or script it runs. It will likely point to a shell script.

3. Examine the shell script that the cron job executes:
```
>    cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv


   This script will reveal what it’s doing. It might be copying or writing something to a temporary file.

4. Follow the path revealed in the script:

   ``````
>cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

   This temporary file will contain the password for the next level.

## Conclusion

After reading the temporary file, you’ll have the password for Bandit Level 21. Good luck on the next challenge!
