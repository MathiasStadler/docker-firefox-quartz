## run ff out of a vmvirtual arch box

# install Xquartz on your local mac

# install virtualbox on your local mac

# install vagrant on your local mac

# download and run a arch box in your virtualbox installation

# check you can login 

```bash
vagrant ssh
```

# check you can login via openssh 

- you will find the informartion for the ssh login in the ouput vagarnt ssh-config

```bash
ssh -i <maschine private key> -X -p <maschine port> vagrant@127.0.0.1
```

## install docker on the virtual arch box

## allow remote seesion in xquartz 

-hint  from here - https://sourabhbajaj.com/blog/2017/02/07/gui-applications-docker-mac/ 

## detect virtualbox ip

- rn command on virtaul box

```bash
IP=$(ifconfig en0 | grep inet | awk '$1=="inet" {print $2}')
echo $IP
``` 
D
## set xhost + $IP

```bash
xhost + $IP

```
	
