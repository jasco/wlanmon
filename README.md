# Network Interface Monitor and Restart Daemon

Monitor network interface for connectivity and restart if interface is down
(loss of IP address).

## Installation

Copy script wlanmon to target directory.

    cp wlanmon /usr/local/bin/
    chown root.root /usr/local/bin/wlanmon
    chmod 555 /usr/local/bin/wlanmon

If interface to monitor is not wlan0, change INTERFACE variable in the script.

Run as a cron job in crontab, scheduling a check every 15 minutes.

    sudo crontab -e
    */15 * * * * /bin/bash /usr/local/bin/wlanmon
