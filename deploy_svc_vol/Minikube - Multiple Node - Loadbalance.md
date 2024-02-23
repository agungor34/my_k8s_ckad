# Minikube & Multiple Node & Loadbalancer
```
$ minikube start -n=3
```



```
$ minikube tunnel
* Tunnel successfully started

* NOTE: Please do not close this terminal as this process must stay alive for the tunnel to be accessible ...

* Starting tunnel for service hello-minikube1.
* Stopping tunnel for service hello-minikube1.
* Starting tunnel for service web-flask-svc.
* Stopping tunnel for service web-flask-svc.
```

```
$ minikube service web-flask-svc
|-----------|---------------|-------------|---------------------------|
| NAMESPACE |     NAME      | TARGET PORT |            URL            |
|-----------|---------------|-------------|---------------------------|
| default   | web-flask-svc |        3000 | http://192.168.49.2:32555 |
|-----------|---------------|-------------|---------------------------|
* Starting tunnel for service web-flask-svc.
|-----------|---------------|-------------|------------------------|
| NAMESPACE |     NAME      | TARGET PORT |          URL           |
|-----------|---------------|-------------|------------------------|
| default   | web-flask-svc |             | http://127.0.0.1:60100 |
|-----------|---------------|-------------|------------------------|
* Opening service default/web-flask-svc in default browser...
! Because you are using a Docker driver on windows, the terminal needs to be open to run it.
```

```
$ minikube ssh
docker@minikube:~$ cd /tmp
cd /tmp
docker@minikube:/tmp$ ls
ls
gvisor  h.1507  h.1569  hostpath-provisioner  hostpath_pv
docker@minikube:/tmp$ cd hostpath-provisioner
cd hostpath-provisioner
docker@minikube:/tmp/hostpath-provisioner$ ls
ls
default
docker@minikube:/tmp/hostpath-provisioner$ cd default
cd default
docker@minikube:/tmp/hostpath-provisioner/default$ ls
ls
pvc-from-standart-sc
docker@minikube:/tmp/hostpath-provisioner/default$ cd pvc-from-standart-sc
cd pvc-from-standart-sc
docker@minikube:/tmp/hostpath-provisioner/default/pvc-from-standart-sc$ ls
ls
docker@minikube:/tmp/hostpath-provisioner/default/pvc-from-standart-sc$ pwd
pwd
/tmp/hostpath-provisioner/default/pvc-from-standart-sc
docker@minikube:/tmp/hostpath-provisioner/default/pvc-from-standart-sc$

docker@minikube:/tmp/hostpath-provisioner/default/pvc-from-standart-sc$ echo "Wilkommen Akif's Welt" > index.html
lkommen Akif's Welt" > index.html
docker@minikube:/tmp/hostpath-provisioner/default/pvc-from-standart-sc$ ls
ls
index.html
docker@minikube:/tmp/hostpath-provisioner/default/pvc-from-standart-sc$ ls -l
ls -l
total 4
-rw-r--r-- 1 docker docker 22 Feb 23 21:57 index.html
docker@minikube:/tmp/hostpath-provisioner/default/pvc-from-standart-sc$
```