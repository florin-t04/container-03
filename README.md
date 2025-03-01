# container-03
# Denumirea lucrării de laborator: Prima aplicație Docker

## Scopul lucrării: Aceasta lucrare de laborator familiarizează cu elementele de bază ale containerizării și pregătește spațiul de lucru pentru următoarele lucrări de laborator.

## Sarcina: Instalarea Docker Desktop și verificarea funcționării acestuia.

## Descrierea executării lucrării cu răspunsuri la întrebări:
   1. Pregătire
Am descărcat și instalat Docker Desktop. 
   2. Executare
Am creat un repozitoriu containers03 și l-am clonat pe computer.
În directorul containers03, am creat fișierul Dockerfile cu următorul conținut:
FROM debian:latest  
COPY ./site/ /var/www/html/  
CMD ["sh", "-c", "echo hello from $HOSTNAME"]  
În același director de proiect, am creat directorul site. În acest director, am adăugat fișierul index.html cu un conținut arbitrar.
   3. Pornire și testare
Am deschis terminalul în directorul containers03 și am executat comanda:
docker build -t containers03 .
*Cât timp a durat crearea imaginii?*
    13.8s

Apoi, am executat comanda pentru a porni containerul:
docker run --name containers03 containers03
*Ce a fost afișat în consolă?*
    hello from 61ac519f0c59



Pentru a șterge containerul și a-l porni din nou, am rulat comenzile:
docker rm containers03  
docker run -ti --name containers03 containers03 bash  
În fereastra deschisă, am executat comenzile:

cd /var/www/html/  
ls -l  

*Ce este afișat pe ecran?*

    ```bash
    root@6fd7878f0798:/# cd /var/www/html/
    root@6fd7878f0798:/var/www/html# cd /var/www/html/
    root@6fd7878f0798:/var/www/html# ls -l
    total 0
    -rwxr-xr-x 1 root root 0 Mar  1 07:59 index.html
    root@6fd7878f0798:/var/www/html#
    ```

În final, am închis fereastra cu comanda:
exit  


## Concluzii
    - Am învățat cum să creăm și să gestionăm un container Docker folosind un fișier Dockerfile.
    - Am explorat procesul de copiere a fișierelor într-un container și modul în care acestea sunt accesate.
    - Am utilizat comenzi Docker esențiale pentru construire, rulare și administrare a containerelor.


Bibliografie
https://moodle.usm.md/mod/assign/view.php?id=282515
https://www.docker.com/

