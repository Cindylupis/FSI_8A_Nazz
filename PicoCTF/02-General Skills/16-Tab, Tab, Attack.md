### **Descripción**
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames.[Addadshashanammu.zip](https://challenge-files.picoctf.net/c_wily_courier/c090282eec93405912f926586287741dd5b9bd24cbdf8f3555c53902d556e508/Addadshashanammu.zip)

## Solución

**Solución 1- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/c090282eec93405912f926586287741dd5b9bd24cbdf8f3555c53902d556e508/Addadshashanammu.zip
--2026-02-12 14:58:23--  https://challenge-files.picoctf.net/c_wily_courier/c090282eec93405912f926586287741dd5b9bd24cbdf8f3555c53902d556e508/Addadshashanammu.zip
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.95, 3.160.5.40, 3.160.5.64, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 5166 (5.0K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip 100%[=====================>]   5.04K  --.-KB/s    in 0s      

2026-02-12 14:58:23 (1.27 GB/s) - 'Addadshashanammu.zip' saved [5166/5166]

NazaretEsquivel-picoctf@webshell:~$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
 extracting: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet.c  
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
NazaretEsquivel-picoctf@webshell:~$ cd Addadshashanammu/
NazaretEsquivel-picoctf@webshell:~/Addadshashanammu$ cd Almurbalarammi/Ashalmimilkala/
NazaretEsquivel-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala$ 
cd Assurnabitashpi/
NazaretEsquivel-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/A
ssurnabitashpi$ cd Maelkashishi/
NazaretEsquivel-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi$ cd Onnissiralis/
NazaretEsquivel-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis$ cd Ularradallaku/
NazaretEsquivel-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet  fang-of-haynekhtnamet.c
NazaretEsquivel-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ chmod +x fang-of-haynekhtnamet
NazaretEsquivel-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_fc588427}

```

#### NOTAS
Usamos el comando `unzip` para extraer las carpetas. Verás que se crean muchísimos niveles de directorios.
Al presionar la tecla **Tab**. La terminal completará el nombre largo automáticamente.
Dale permisos y ejecútar : chmod +x fang-of-haynekhtnamet
./fang-of-haynekhtnamet