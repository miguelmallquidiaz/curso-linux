# Concepto básicos
  CLI `(Interfaz de linea de comando)` puedes ejecutar un proceso en el sistema operativo y hace que el ordenador realize una tarea determinada.

  La mayotia de los comandos siguen esta sintaxis `comando [opciones] [argumentos]`
  - Comando: Es el nombre del programa que deseas ejecutar. Por ejemplo, ls, cd, mkdir, etc. Este es el elemento principal que le dice al sistema qué acción realizar.
  - opciones: Son indicadores que alteran el comportamiento predeterminado del comando. Por lo general, se especifican precedidos por un guion (-) o dos guiones (--).
  - argumento: Son elemento o valores que debe actuar el comando,  son los datos que el comando utilizará para realizar una acción específica. Los argumentos pueden ser nombres de archivos, directorios, valores numéricos u otra información 

# comandos
Ejemplo de comando:
```
ls: Muestra información sobre los archivos contenidos en el directorio actual
```
Ejemplo para argumento:
```
ls Documents
```
Ejemplo de opciones:

`ls -l (proporciona información de los archivos)`

```
sysadmin@localhost:~$ ls -l
total 32
drwx------ 2 sysadmin sysadmin 4096 Dec 20  2017 Desktop                        
drwx------ 4 sysadmin sysadmin 4096 Dec 20  2017 Documents                      
drwx------ 2 sysadmin sysadmin 4096 Dec 20  2017 Downloads                      
drwx------ 2 sysadmin sysadmin 4096 Dec 20  2017 Music                          
drwx------ 2 sysadmin sysadmin 4096 Dec 20  2017 Pictures                       
drwx------ 2 sysadmin sysadmin 4096 Dec 20  2017 Public                         
drwx------ 2 sysadmin sysadmin 4096 Dec 20  2017 Templates                      
drwx------ 2 sysadmin sysadmin 4096 Dec 20  2017 Videos
```

`ls -r (imprime en un orden alfabrtico inverso)`

```
sysadmin@localhost:~$ ls -r
Videos  Templates  Public  Pictures  Music  Downloads  Documents  Desktop
```

```
Se pueden utilizar combinaciones
ls -l -r
ls -rl
ls -lr
```
## Directorio
sintaxis pwd [opcion]
`pwd (imprime el directorio de trabajo)`
Estructura del sistema de archivos
![directorio](https://github.com/miguelmallquidiaz/curso-linux/blob/main/NDG-Linux-Unhatched/directorio.png)

## Cambio de directorio:
sintaxis cd [opciones] [rutas]
`cd (cambiar en el directorio)`
## Rutas absolutas:
Especificar la ruta exacta de un directorio
```
sysadmin@localhost:/$ cd /home/sysadmin  
```
## Rutas relativas:
Comienza con el directoio actual sin el / al princio
```
sysadmin@localhost:/$ cd Documents  
```

## Atajos

`cd .. (Retrocede un directorio)`

`cd ~ (Regresa al directorio sysadmin)`

## Listado de archivos:

Sintaxis: ls [OPCIONES] [ARCHIVO]

`ls -l /var/log/ (Me muestra más información del tipo de archivo)`

```
sysadmin@localhost:~$ ls -l /var/log/
total 844                                                                       
-rw-r--r-- 1 root   root  18047 Dec 20  2017 alternatives.log                   
drwxr-x--- 2 root   adm    4096 Dec 20  2017 apache2                            
drwxr-xr-x 1 root   root   4096 Dec 20  2017 apt                                
-rw-r----- 1 syslog adm    1346 Oct  2 22:17 auth.log                           
-rw-r--r-- 1 root   root  47816 Dec  7  2017 bootstrap.log                      
-rw-rw---- 1 root   utmp      0 Dec  7  2017 btmp                               
-rw-r----- 1 syslog adm     547 Oct  2 22:17 cron.log                           
-rw-r----- 1 root   adm   85083 Dec 20  2017 dmesg                              
-rw-r--r-- 1 root   root 325238 Dec 20  2017 dpkg.log                           
-rw-r--r-- 1 root   root  32064 Dec 20  2017 faillog                            
drwxr-xr-x 2 root   root   4096 Dec  7  2017 fsck                               
-rw-r----- 1 syslog adm     106 Oct  2 19:57 kern.log                           
-rw-rw-r-- 1 root   utmp 292584 Oct  2 19:57 lastlog                            
-rw-r----- 1 syslog adm   19573 Oct  2 22:57 syslog                             
drwxr-xr-x 2 root   root   4096 Apr 11  2014 upstart                            
-rw-rw-r-- 1 root   utmp    384 Oct  2 19:57 wtmp   
```

## Tabla de tipos de archivos

| Símbolo | Tipo de archivo | Descripción |
|---|---|---|
| d | directorio | Un archivo usado para contener otros archivos. |
| - | archivo ordinario | Incluye archivos leíbles, imágenes, archivos binarios, y archivos comprimidos. |
| l | enlace simbólico | Apunta a otro archivo. |
| s | socket | Permite la comunicación entre procesos. |
| p | tubería (pipe) | Permite la comunicación entre procesos. |
| b | archivo bloque | Usado para comunicaciones con el equipo (hardware). |
| c | archivo carácter | Usado para comunicaciones con el equipo (hardware). |

### Tipo de archivo
El primer carácter de esta salida indica el tipo de archivo. Recuerde que si el primer carácter es un -, este es un archivo ordinario. Si el carácter fuera una d, se trataría de un directorio.
(-) rw-r--r-- (Es un archivo normal)

### Permisos: 

Los permisos indican cómo determinados usuarios pueden acceder a un archivo. Siga leyendo para obtener más información sobre los permisos

d (rwxr-xr-x) 2 root   root   4096 Apr 11  2014 upstart

### Número de enlaces directos:

Este número indica cuántos enlaces directos apuntan a este archivo. Los enlaces directos están fuera del alcance de este módulo,

-rw-r----- (1) syslog adm    1346 Oct  2 22:17 auth.log

### Propietario del archivo

-rw-r----- 1 (syslog) adm     106 Oct  2 19:57 kern.log

El usuario syslog posee este archivo. Cada vez que se crea un archivo, la propiedad se asigna automáticamente al usuario que lo creó.

### Grupo propietario del archivo: Indica qué grupo posee este archivo.

-rw-rw-r-- 1 root   (utmp) 292584 Oct  2 19:57 lastlog

### Tamaño del archivo: Los directorios y archivos más grandes pueden mostrarse en kilobytes ya que mostrar su tamaño en bytes resultaría en un número demasiado grande

-rw-r----- 1 syslog adm   (19573) Oct  2 22:57 syslog

### Sello horario o de tiempo:
Indica la fecha y hora en que el contenido del archivo se modificó por última vez.

drwxr-xr-x 2 root   root   4096 (Dec  7  2017) fsck

### Nombre del archivo: El campo final contiene el nombre del archivo o directorio.

-rw-r--r-- 1 root   root  47816 Dec  7  2017 (bootstrap.log)

## Acceso administrativo:

Ingresas como usuario root proporciona acceso administrativo
`su OPCIONES NOMBRE-DE-USUARIO`
El comando `exit` te permite regresar al usuario normal

El comando `sudo` sólo proporciona acceso administrativo para la ejecución del comando especificado, pero no te cambia de usuario
Sintaxis: `sudo [Opciones] comando`

## Permisos
Son los permisos que el usuario tiene con los archivos o directorios

| Permiso | Archivos | Directorios |
|---|---|---|
| leer (read) (r)	 | Leer o copiar contenido | Listar archivos sin detalle (o detallado con ls -l si se tiene permiso de ejecución) |
| escribir (write) (w) | Modificar o reescribir contenido | Añadir o eliminar archivos (requiere permiso de escritura en el directorio padre) |
| ejecutar (execute) (x) | Ejecutar como proceso | Cambiar al directorio (requiere permiso de escritura en el directorio padre) |

### Propietario:
Si la cuenta es del propietario se usara el primer grupo de permisos y los demás no

`- (rw-) r--r-- 1 sysadmin sysadmin 647 Dec 20  2017 hello.sh`

### Grupo:
Si es miembro del grupo se aplicara los permisos de grupo 

`- rw- (r--) r-- 1 sysadmin sysadmin 647 Dec 20  2017 hello.sh`

### Otros

Si no pertenece a los 2 anteriores se aplicara el tercer permiso
`- rw- r-- (r--) 1 sysadmin sysadmin 647 Dec 20  2017 hello.sh`

## Cambiar los permisos de los archivos:
Sólo el usuario raíz o el usuario propietario del archivo puede cambiar los permisos de un archivo o directorio.

### método simbólico
El método simbólico es útil para cambiar un conjunto de permisos a la misma vez.

Sintaxis: `chmod [<COJUNTO DE PERMISOS><ACCIÓN><PERMISOS>]... ARCHIVO`

### Conjunto de permisos:

|Símbolo|Significado|
|:----|:----|
|u|Usuario: El usuario propietario del archivo.|
|g|Grupo: El grupo propietario del archivo.|
|o|Otros: Cualquier otro que no sea el usuario propietario o un miembro del grupo propietario.|
|a|Todos: Se refiere al usuario, grupo, y todos los demás.|

### Acción

|Símbolo|Significado|
|:----|:----|
|+|Añadir permiso, si es necesario|
|=|Especificar el permiso exacto|
|-|Eliminar el permiso, si es necesario|

### Permisos

|Símbolo|Significado|
|:----|:----|
|r|leer (read)|
|w|escribir (write)|
|x|ejecutar (execute)|

### Archivo:
Finalmente, añada un espacio y los nombres de ruta para los archivos a los que quiere asignar los permisos.

`chmod [<CONJUNTO DE PERMISOS><ACCIÓN><PERMISOS>]... ARCHIVO`

Ejemplo: 

`sysadmin@localhost:~/Documents$ chmod u+x hello.sh`

./hello.sh
Esto indica que el “comando” debe ejecutarse desde el directorio actual.

## Cambiar el propietario de un archivo

chown se utiliza para cambiar el propietario de los archivos y directorios. requiere acceso administrativo

`chown [OPCIONES] [PROPIETARIO] ARCHIVO`

- El primer argumento, [PROPIETARIO], especifica qué usuario debe ser el nuevo propietario.
- El segundo argumento, ARCHIVO, especifica el archivo al cual se está cambiando el propietario.

Ejemplo: Se cambbio el propierta del archivo a root
```
sysadmin@localhost:~/Documents$ ls -l hello.sh                                  
-rwxr--r-- 1 sysadmin sysadmin 647 Dec 20  2017 hello.sh                        
sysadmin@localhost:~/Documents$ sudo chown root hello.sh                                                   
sysadmin@localhost:~/Documents$ ls -l hello.sh                                  
-rwxr--r-- 1 root sysadmin 647 Dec 20  2017 hello.sh 
```

## Visualización de archivos

`cat` se utiliza para ver rapidamente el contenido de archivos pequeños
- Solo muestra 5 lineas

Sintaxis: `cat [OPCIONES] [ARCHIVO]`

Para ver archivos largos `more` y `less`

Estos comandos head y tail son utiles para ver los archivos de registro del sistema

Para visualizar solamente las 10 primeras líneas del resultado anterior para el archivo alpha.txt, utilice el comando head
```
sysadmin@localhost:~/Documents$ head alpha.txt                          
A is for Apple                                                        
B is for Bear                                                         
C is for Cat                                                        
D is for Dog                                                         
E is for Elephant                                                     
F is for Flower                                                       
G is for Grapes                                                        
H is for Happy                                                        
I is for Ink                                                          
J is for Juice`
```
Para visualizar las 10 ultimas líneas se utiliza tail:

```
sysadmin@localhost:~/Documents$ tail alpha.txt                          
Q is for Quark                                                         
R is for Rat                                                           
S is for Sloth                                                        
T is for Turnip                                                        
U is for Up                                                            
V is for Velvet                                                      
W is for Walrus                                                        
X is for Xenon                                                        
Y is for Yellow                                                        
Z is for Zebra`
```
Se puede especificar la cantidad e lineas que quieres visualizar: 
Sintaxis:
- `head -n número_de_líneas archivo`
- `tail -n número_de_líneas archivo`


```
sysadmin@localhost:~/Documents$ head -n 5 alpha.txt                    
A is for Apple                                                         
B is for Bear                                                          
C is for Cat                                                           
D is for Dog                                                           
E is for Elephant
```

## Copiar archivos
Se utiliza para copiar archivos

Sintaxis: `cp [OPCIONES] ORIGEN DESTINO`

`sysadmin@localhost:~/Documents$ cp /etc/passwd .`

Nota: 

El segundo argumento es el carácter (.). Recuerde la sección Cambio de Directorio, este carácter es un atajo al directorio actual.

### Copiar archivos o particiones enteras:

Sintaxis: `dd [OPCIONES] OPERANDO`

- Se puede usar para clonar o eliminar (wipe) discos o particiones enteras.

```
sysadmin@localhost:~$ dd if=/dev/zero of=/tmp/swapex bs=1M count=50 
50+0 records in
50+0 records out
52428800 bytes (52 MB) copied, 0.825745 s, 635 MB/s
```

- if: El archivo de entrada que se va a leer
- of: El archivo de salida que se va a escribir
- bs: tamaño de bloque que se va a utilizar. No es necesario escribirlo al clonar un disco duro
- count: El número de rencuentro que se va a leer desde el archivo de entrada. Igual no es necesario

## Mover archivos:
Mover un archivo de una ubicación a otra.

Sintaxis: `mv ORIGEN DESTINO`

Ejemplo:

1. Mover un archivo al directorio
`sysadmin@localhost:~/Documents$ mv people.csv Work`
2. Mover varios archvios aun directorio
`sysadmin@localhost:~/Documents$ mv numbers.txt letters.txt alpha.txt School`
3. Cambiar el nombre al mover un archivo al mismo directorio
`mv animals.txt zoo.txt`

## Eliminar archivos

El comnado rm se utiliza para eliminar archivos y directorios se elimina de manera permanente

Sintaxis: `rm [OPCIONES] ARCHIVO`

Tambien impide remover directorio tienes que poner `-r` o `-R` tener cuidado esta opción es recursiva
ya que elimina todos los archivos o subdirectorios.

## Filtrado de entradas

Buscar lineas de una condición y te devolvera aquellas que coincidan

Sintaxis: `grep [OPCIONES] PATRÓN [ARCHIVO]`

Ejemplo:

1. Utilizar para filtrar y obtener información de un usuario especifico
```
sysadmin@localhost:~/Documents$ grep sysadmin passwd                               
sysadmin:x:1001:1001:System Administrator,,,,:/home/sysadmin:/bin/bash
```

## Expresiones regulares:

Tabla de expresiones regulares:

|Caracteres Básicos Regex|Significado|
|:----|:----|
|.|Cualquier carácter individual|
|[ ]|Cualquier carácter especificado|
|[^]|Cualquier carácter que no es el carácter especificado|
|*|Cero o más del carácter anterior|
|^|Si es el primer carácter del patrón, el patrón deberá estar al principio de la línea para coincidir, si no es así se tratará como un ^ literal.|
|$|Si es el último carácter del patrón, el patrón deberá estar al final de la línea para coincidir, si no es así se tratará como un $ literal.|


tabla de expresiones regulares extendidas:

|Caracteres Básicos Regex|Significado|
|:----|:----|
|+|Uno o más del patrón anterior|
|?|El patrón es opcional|
|{ }|Especificar mínimo, máximo, o coincidencias exactas en el patrón anterior|
|||Alternancia - el “o” lógico|
|( )|Se usa para crear grupos|

### Caracteres de anclaje:

Limita los resultados de busqueda. Se debe poner en comilla simple

```
sysadmin@localhost:~/Documents$ grep 'root' passwd
root:x:0:0:root:/root:/bin/bash                                                 
operator:x:1000:37::/root:
```
- El primer carácter de anclaje ^ se utiliza para indicar que el patrón debe aparecer al principio de la línea

Ejemplo: 

```
sysadmin@localhost:~/Documents$ grep '^root' /etc/passwd
root:x:0:0:root:/root:/bin/bash
```
El segundo carácter de anclaje $ se puede utilizar para indicar que el patrón debe aparecer al final de la línea

```
sysadmin@localhost:~/Documents$ grep 'r$' alpha-first.txt
B is for Bear
F is for Flower
```

El tercero encontrará cualquier línea que contenga la letra r o f y los puntos representa cualquier caracter

```
sysadmin@localhost:~/Documents$ grep 'r..d' red.txt
reed
read
```

Los corchetes [ ] se utilizan para indicar caracteres únicos o rangos de caracteres posibles en una lista.
utilice el patrón [0123456789] o [0-9]:

```
sysadmin@localhost:~/Documents$ grep '[0-9]' profile.txt
I am 37 years old.
3121991
I have 2 dogs.
123456789101112
```

encontrar todas las líneas que contienen caracteres no numéricos, inserte un ^ como primer carácter dentro de los corchetes

```
sysadmin@localhost:~/Documents$ grep '[^0-9]' profile.txt
Hello my name is Joe.
I am 37 years old.
My favorite food is avocados.
I have 2 dogs.
```

El carácter de expresión regular * se utiliza para indicar la ausencia o la presencia una o más veces del carácter o patrón que lo precede

```
sysadmin@localhost:~/Documents$ grep 're*d' red.txt
red
reeed
rd
reed
```

## Apagar
El comando shutdown prepara al sistema para un apagado seguro, todos los usuarios reciben una notificación del sistema apagandose

Sintaxis: `shutdown [OPCIONES] HORA [MENSAJE]`

`root@localhost:~# shutdown now`

Los formatos de este argumento de tiempo pueden ser la palabra now (ahora), una hora del día en el formato hh:mm o el número de minutos de retraso utilizando el formato +minutos.

Piense sobre lo siguiente

El reloj de nuestro sistema puede estar configurado en una zona horaria diferente a la que se encuentra usted. Para verificar la hora en la terminal, use el comando date. En nuestras máquinas, el formato predeterminado de la salida del comando date es el siguiente:

`dia_de_la_semana  mes  hora:minuto:segundo  UTC  año` 

o en ingles:

`weekday month day hour:minute:second UTC year`

Las letras UTC presentes en la salida indican que la hora se muestra de acuerdo con el Horario Coordinado Universal.

`root@localhost:~# shutdown 01:51`

Este mensaje aparecerá en las terminales de todos los usuarios. Por ejemplo:

`root@localhost:~# shutdown +1 "Goodbye World!"`

