## CronTab 
This sets the cronjob to run every 2 hours
> This is currently set to 2 hours as I am on holiday and do not have direct access to the server

`0 */2 * * * /usr/local/bin/sensors-mail.sh`


## sensors-mail.sh
This is the shell script being made to run every x hours, It sends an email to my personal account from my learning / professional account
Inside the email it has the results from my temperature sensor


```
#!/bin/bash
{
  echo "To: Ollie's-Personal-Email.com"
  echo "From: ollie@olliebrown.nz"
  echo "Subject: Sensors report from $(hostname) - $(date '+%Y-%m-%d %H:%M')"
  echo ""
  /usr/bin/sensors
} | /usr/bin/msmtp -t``
