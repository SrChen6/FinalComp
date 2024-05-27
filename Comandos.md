# Comandas de Terminal
## Basicas
1. `cp file destination`
copia el archivo a donde le dices
2. `mv file destination`
Mueve los archivos `-i` hace que pregunte antes de sobrescibir. Sirve para cambiar el nombre tambien
3. `mkdir directory`
Crea una carpeta
4. `rm file1 file2 ...`
Borra cosas. `-f` para forzar, y `-r` para recursivo (borrar carpetas basically)
5. `gcc`
Compila C. Merece mas explicacion luego.
6. `grep`
Para buscar texto en archivos, o lo que le pases de input con `|` (tiene opciones y eso no se como va)
7. `echo`
Escribe en terminal el argumento
8. `tar`
Para comprimir, ya te dicen como tiene que ser.
9. `ls`
Lista los archivos y directorios en el directorio actual. `-l` para formato largo, `-a` para mostrar archivos ocultos.
10. `cd directorio`
Cambia el directorio al que especificas.
11. `pwd`
Muestra el directorio actual.
12. `cat file`
Muestra el contenido del archivo.
13. `nano file`
Abre el archivo en el editor de texto
14. `man comanda`
Te da mas info sobre el comando.
15. `kill`
Envía una señal a un proceso. Por ejemplo, `kill -9 PID` envía la señal SIGKILL al proceso con el PID especificado.
(mata cosas)
16. `ldd`
Escribe las librerías enlazadas dinámicamente.
17. `/usr/bin/time ./executable.exe
Devuelve el tiempo transcurrido en la ejecución.

## GCC

1. `gcc file.c`
Compila el archivo `file.c` y genera un ejecutable  `a.out`.
2. `gcc -o output file.c`
Compila `file.c` y genera un ejecutable con el nombre `output`.
3. `gcc -c file.c`
Compila `file.c` y genera un archivo de objeto `file.o`.
4. `gcc -S file.c`
Compila `file.c` y genera un archivo de ensamblador `file.s`.
5. `gcc file1.o file2.o -o output`
Enlaza los archivos de objeto `file1.o` y `file2.o` para generar un ejecutable `output`.
6. `gcc -lmylib file.c`
Compila el archivo `file.c` y enlaza la biblioteca `libmylib.a` o `libmylib.so`.
7. `gcc -L/mylibs -lmylib file.c`
Compila el archivo `file.c` y enlaza la biblioteca `libmylib.a` o `libmylib.so` que se encuentra en el directorio `/mylibs`.
8. `gcc -static -o output file.c -lmylib`
Compila el archivo `file.c`, enlaza la biblioteca estática `libmylib.a` y genera un ejecutable llamado `output`.
9. `gcc -shared -o libmylib.so file1.o file2.o`
Genera una biblioteca compartida `libmylib.so` a partir de los archivos de objeto `file1.o` y `file2.o`.
10. `gcc -Wall file.c`
Compila el archivo `file.c` y muestra todos los avisos de compilación.
11. `gcc --help --verbose`
Muestra la ayuda del compilador y subprocesos. ¡Muy útil!
12. `gcc -fpic file.c`
Genera código independiente de la posición – modo pequeño. Necesario para construir bibliotecas compartidas.
13. `gcc -fPIC file.c`
Genera código independiente de la posición – modo grande. Para bibliotecas compartidas.
14. `gcc -g file.c`
Genera información de depuración, útil para gdb, ddd, etc.
15. `gcc -L<path> file.c`
Añade la ruta a la lista de directorios donde encontrar bibliotecas para el enlace.
16. `gcc -l<name> file.c`
Añade lib<name>.so para el enlace compartido, y/o lib<name>.a para el enlace estático.
17. `gcc -shared file.c`
Genera una biblioteca compartida, en lugar de un ejecutable binario.
18. `gcc -static file.c`
Genera un ejecutable binario enlazado estáticamente.


## Otras
1. `lstopo`
Se usa para saber el numero de CPUs, cores, etc.
2. `top`
Administrador de tareas basically, mucha info (memoria, cpu usada, PID, prioridad, etc.)
Con `-p PID` puedes especificar que muestre un proceso solo.
3. `ps`
Muestra info sobre procesos. `-e` para mostrar todos. con `-o` le puedes pedir algunas info en particular creo.
4. `nm`
Ensenya la taula de simbolos d'un arxiu compilado.
4. `chmod`
Cambia los permisos de un archivo o directorio. Por ejemplo, `chmod 755 file` establece los permisos de lectura, escritura y ejecución para el propietario, y de lectura y ejecución para el grupo y otros.
5. `lscpu`
Muestra información detallada sobre la CPU.
6. `lsblk`
Muestra información sobre los dispositivos de bloque (discos y particiones).
