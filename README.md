# Installation

```
# Host
$ dokku apps:create jenkins
$ cd /var/lib/dokku/data/storage
$ mkdir jenkins jenkins_home
$ sudo chown -R dokku:dokku jenkins jenkins_home
$ sudo chown -R dokku:dokku /var/run/docker.sock
$ sudo chmod -R 777 jenkins jenkins_home
$ sudo chmod -R 777 /var/run/docker.sock
$ sudo dokku storage:mount jenkins /var/lib/dokku/data/storage/jenkins:/var/jenkins_home
$ sudo dokku storage:mount jenkins /var/lib/dokku/data/storage/jenkins_home:/home
$ sudo dokku storage:mount jenkins /var/run/docker.sock:/var/run/docker.sock
$ sudo dokku proxy:ports-add jenkins http:8080:8080
$ sudo dokku proxy:ports-add jenkins http:50000:50000

# Local
$ git remote add dokku dokku@host_ip:jenkins
$ git push origin dokku
```
