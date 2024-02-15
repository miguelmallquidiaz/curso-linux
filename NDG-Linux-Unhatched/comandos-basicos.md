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

