### Service commands:
```bash
#start service
service httpd start
or
systemctl start http

#stop service
systemctl stop httpd

#check status
systemctl status httpd

#configure to start on startup
systemctl enable httpd

@configure to not start on startup
systemctl disable httpd
```

### Configure an app as a service
The app must be configured as a **systemd** service. You can use this to automatically start a python web-server or whatever. A system dservice is configured using a systemd unit file Typically found: **/etc/systemd/system**

#### **Create a new file in this directory:**
![[Pasted image 20230126161423.png]]

```bash
#**Reload daemon to register new service**
systemctl daemon-reload

#start app as service
systemctl start my_app
```

### Example docker Service Unit File
![[Pasted image 20230126161434.png]]