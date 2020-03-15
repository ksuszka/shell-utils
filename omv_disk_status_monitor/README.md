# monitor_disk_status

*monitor_disk_status* is a script which uses hdparm utility to check spinning
status of each disk without waking it up.

# Usage

To test it, just run `sudo ./monitor_disk_status`

# Using script as a daemon

## Daemon Installation

Script was prepared to run as a simple deamon on my OMV5 based media server.

- copy `monitor_disk_status` file to /usr/sbin directory
- copy `monitor_disk_status` file to /etc/systemd/system directory
- run following commands to start service:

```
# Reload systemd configuraiton
systemctl daemon-reload

# Configure service to be run at startup
systemctl enable monitor_disk_status

# Start service immediately
systemctl start monitor_disk_status
```

## Usage

To view log files use following command:

```
journalctl -f -u monitor_disk_status
```
