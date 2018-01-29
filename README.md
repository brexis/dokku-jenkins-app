# Installation

```
# Host
$ dokku apps:create jenkins
$ cd /var/lib/dokku/data/storage
$ mkdir jenkins jenkins_home
$ chown -R dokku:dokku jenkins jenkins_home
$ chmode -R 777 jenkins jenkins_home
$ dokku docker-options:add jenkins deploy,run "-v /var/lib/dokku/data/storage/jenkins:/var/jenkins_home"
$ dokku docker-options:add jenkins deploy,run "-v /var/lib/dokku/data/storage/jenkins_home:/home"
$ dokku docker-options:add jenkins deploy,run "-v /var/run/docker.sock:/var/run/docker.sock"
$ dokku proxy:ports jenkins http:8080:8080
$ dokku proxy:ports jenkins http:50000:50000

# Local
$ git add remote dokku@host_ip:jenkins
$ git push origin dokku
```
