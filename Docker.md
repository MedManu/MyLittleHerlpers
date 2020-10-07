#								Docker 

### Images:

- Templets woraus Container Instanzen erstellt werden  

- besteht aus: SorceCode, Libraries und Binärdaten
- aus einem Image können mehrer Container erstellt werden 

### Container:

Ist laufende Instanz einer Images

 ## für netbeans:  socat tcp-listen:9090,fork UNIX:///var/run/docker.sock



```bash
Docker
```

- Gint allg. Übersicht über die Befehle

```bash
Docker container run --publish  8080:80 nginx
```

-  nginx ist das IMAGE
- unser Localhost 8080 
- Port mit dem wir den Host ansprechen
- --publish/-p öffentlich
- Es wird ein Container basierend auf dem IMAGE nginx erzeugt

## Container anzeigen: 

- docker container ls
  - docker conatainer ls -a

   - docker ps

     

## Logs anzeigen:

- docker logs "containerName oder id"
- =3w0ptyb0kIhyLK4rDILiMr0fBI

## commands inside docker

-  docker exec -it mySQL1 mysql -uroot -p  
- $ docker exec -it mySQL1 bash --> um es im terminal zu auszufüllen
  -  mysql -uroot -p  --> befehl für anmeldung mit passwort

