# kitura-upstart-script
An upstart script to start the Kitura app server.

## Getting Started

* Place the [kitura-server.conf](https://github.com/SwathiMystery/kitura-upstart-script/blob/master/kitura-server.conf) file in `/etc/init/` path.
* Run the following command to check if the syntax is OK.
```
$ init-checkconf /etc/init/kitura-server.conf 
File /etc/init/kitura-server.conf: syntax ok
```
* Symlink to `/etc/init.d` for autocompletion
```
sudo ln -s /etc/init/kitura-server.conf /etc/init.d/kitura-server
```
* You may now play with the following service commands : `(start|stop|status|restart)`
```
$ sudo service kitura-server start
kitura-server start/running, process 28776
$ sudo service kitura-server start
start: Job is already running: kitura-server
$ sudo service kitura-server stop
kitura-server stop/waiting
$ sudo service kitura-server status
kitura-server stop/waiting
$ sudo service kitura-server start
kitura-server start/running, process 28822
$ sudo service kitura-server status
kitura-server start/running, process 28822
$ sudo service kitura-server restart
kitura-server stop/waiting
kitura-server start/running, process 29283
```
* Checking the logs
```
$ tail -f /var/log/kitura-server.log
[2017-01-21T11:02:16.249Z] [VERBOSE] [Kitura.swift:80 start()] Starting an HTTP Server on port 8090...
[2017-01-21T11:02:16.257Z] [INFO] [HTTPServer.swift:83 listen(on:)] Listening on port 8090 (delegate: SSLService.SSLService)
```
* Verify the URL 
