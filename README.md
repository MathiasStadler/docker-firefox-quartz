## run ff out of a vmvirtual arch box

## install Xquartz on your local mac
from here http://fabiorehm.com/blog/2014/09/11/running-gui-apps-with-docker/


## install virtualbox on your local mac

# install vagrant on your local mac

# download and run a arch box in your virtualbox installation

# check you can login 

```bash
vagrant ssh
```

## activate X11Forward for ssh 

- from here https://unix.stackexchange.com/questions/12755/how-to-forward-x-over-ssh-to-run-graphics-applications-remotely 

```bash
# set follow setting in yor /etc/ssh/sshd_config
X11Forwarding yes
X11DisplayOffset 10
```
## restart sshd

```bash
cat /var/run/sshd.pid | sudo xargs kill -1
```

# login via opensshn in the Xquartz terminal 

- you will find the informartion for the ssh login in the ouput vagarnt ssh-config

```bash
ssh -i <maschine private key> -X -p <maschine port> vagrant@127.0.0.1
```

## install docker on the virtual arch box

## install xorg-xhost on the virtual arch box 

```bash
sudo pacman -S xorg-xhost
```
## insatt xauth
```bash
sudo pacman -S xorg-xauth
```
## allow remote seesion in xquartz 

-hint  from here - https://sourabhbajaj.com/blog/2017/02/07/gui-applications-docker-mac/ 

## detect virtualbox ip

- rn command on virtaul box

```bash
IP=$(ip -o route get to 8.8.8.8 | sed -n 's/.*src \([0-9.]\+\).*/\1/p')
echo $IP
``` 
D
## set xhost + $IP

```bash
xhost + $IP
/usr/X11/bin/xhost + $IP
```
	
