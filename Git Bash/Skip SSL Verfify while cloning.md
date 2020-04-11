#### ERROR MSG:
unable to access `https://github.rsa.lab.emc.com/<someRepo>`: server certificate verification failed. CAfile: /home/ecat/Documents/<Some Certificate>.pem CRLfile: none

#### Work Around
```
                   $ git config --global http.sslVerify false
```
