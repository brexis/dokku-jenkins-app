# Installation

```
# Host
$ dokku apps:create jenkins
$ cd /var/lib/dokku/data/storage
$ mkdir jenkins jenkins_home
$ sudo chown -R dokku:dokku jenkins jenkins_home
$ sudo chown -R dokku:dokku /var/run/docker.sock
$ sudo dokku storage:mount jenkins /var/lib/dokku/data/storage/jenkins:/var/jenkins_home
$ sudo dokku storage:mount jenkins /var/lib/dokku/data/storage/jenkins_home:/home
$ sudo dokku storage:mount jenkins /var/run/docker.sock:/var/run/docker.sock
$ dokku proxy:ports-add jenkins http:8080:8080
$ dokku proxy:ports-add jenkins http:50000:50000

# Local
$ git add remote dokku@host_ip:jenkins
$ git push origin dokku
```
