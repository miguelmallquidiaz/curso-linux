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
El método simbólico es útil para cambiar un conjunto de permisos a la misma vez
Sintaxis: 
