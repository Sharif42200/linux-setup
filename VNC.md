# Setup VNC SERVER

First we need to install **x11vnc** and **lightdm**

```
sudo apt update
```

```
sudo apt install lightdm
```

```
sudo reboot
```

```
sudo apt install x11vnc
```

Now **x11vnc.service** needs to be updated and the following configuration needs to be added

```
sudo nano /lib/systemd/system/x11vnc.service
```

OR

```
sudo subl /lib/systemd/system/x11vnc.service
```

Copy Paste the following configuration on **x11vnc.service** file.

```
[Unit]
Description=x11vnc service
After=display-manager.service network.target syslog.target

[Service]
Type=simple
ExecStart=/usr/bin/x11vnc -forever -display :0 -auth guess -passwd password
ExecStop=/usr/bin/killall x11vnc
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

Here, /usr/bin/x11vnc -forever -display :0 -auth guess -passwd **password** needs to be replaced with the actual password.

Then restart all the the services using the following commands.

```
sudo systemctl daemon-reload
```

```
sudo systemctl enable x11vnc.service
```

```
sudo systemctl start x11vnc.service
```

Check the status of the process and find the port number by default it is **5900** .
After that connect with any **VNC** client with ip address and port number and previously configured password

```
sudo systemctl status x11vnc.service
```
