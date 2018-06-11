# formation-jenkins
Date 11-Juin-2018

## Création d'un conteneur slave avec docker
> connection au slave en mode SSH

### le master jenkins 
```
docker exec -it myjenkins bash
ssh-keygen

cat /var/jenkins_home/.ssh/id_rsa.pub
```

### le slave
```
docker run --name slave1 jenkinsci/ssh-slave "content of id_rsa.pub"
docker inspect slave1 | grep IP
```

## sur le master
 - se connecter une fois sur le slave afin d'accepter le certificat et mettre à jour le known host

```
 ssh -i id_rsa jenkins@slaveIP
``` 
