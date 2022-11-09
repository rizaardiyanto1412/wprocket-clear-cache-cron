# Clear WP Rocket cache through Cron

This will give you guide how to clear cache manually on WP Rocket. This method will <b>require to use a cron job</b> on your server

# Installation

1. Download <a href="https://github.com/rizaardiyanto1412/wprocket-clear-cache-cron/blob/main/clear-cache-manual.php">clear-cache-manual.php</a>
2. Upload it to your WordPress root directory. (where wp-config.php and wp-load.php are located).
3. Execute it through your cron job of your server. Different server has it's own way to setup cron job. 
- For the time format, it depends on when you want the script to be executed. For example if you want to execute it everyday on midnight (where there is less activities on your website) you can set it to `0 0 * * * `
In cPanel it should be something like this: <img src="https://i.imgur.com/iBTFE8z.png" height="250px">
You can use something like https://crontab.guru/ to get the exact time.
- For the command, basic command will depend on what you want to do. For example if you want to execute a file, just put the path to the file in the command. Here is the example of how to run it on cPanel: `/usr/local/bin/php /home/username_cpanel/public_html/path/to/cron/script`

This is the full example of how it setup on our server:
<img src="https://i.imgur.com/HPNKj8t.png" height="100px" >

# Troubleshooting

NOTE: I've tested the script and it works on my server. If it does not work, it's either you setup incorrectly or your server cron has an issue. please check the troubleshooting steps below:

1. Does the file correctly placed in the root directory where wp-config.php and wp-load.php are located?
2. Does the path directory in cron command has been correct? 
3. Does the time format correct? 
4. Ultimately, does the cron is running?
You can verify whether it's running or no by creating simple php script, something like `echo "cron is running"` save it as cron-test.php, then call it on cron by outputting the cron. 
This is the example:
![image](https://user-images.githubusercontent.com/83811723/200865481-bc789d1b-c5fa-4c9a-a2cb-91e57f8b38a1.png)
`/usr/local/bin/php /home/u1068875/public_html/2023/cron-test.php > /home/u1068875/public_html/2023/cron-log.txt`
- `/usr/local/bin/php` is php binary path 
- `/home/usernu1068875ame/public_html/2023/cron-test.php` is the php script path, in this case it's my cron-test.php
- `/home/u1068875/public_html/2023/cron-log.txt` is where I want the cron output

If your cron is running, they should output file named cron-log.txt which contain the script
![image](https://user-images.githubusercontent.com/83811723/200866581-985485ea-fcd6-43d5-a0b6-cc6487fdb876.png)

If you did not get the file, please contact your server administrator.

NOTE: This repository is for fulfilling the task from WP Rocket technical assesment (Riza Maulana Ardiyanto)
