# Comandos de C
## General
1. `printf(format, ...)`
Imprime el argumento en la consola. El argumento `format` es una cadena que contiene texto y especificadores de formato como `%d` para enteros, `%f` para flotantes, `%s` para cadenas, etc.
2. `scanf(format, ...)`
Lee el input del usuario. El argumento `format` es una cadena que contiene especificadores de formato similares a `printf`.
3. `main(argc, argv)`
La función principal donde comienza la ejecución del programa. `argc` es el número de argumentos de línea de comandos y `argv` es un array de cadenas que contiene los argumentos.
4. `return value`
Devuelve un valor desde una función. `value` es el valor que se devuelve.
7. `while(condition)`
Ejecuta un bloque de código mientras la `condition` sea verdadera.
8. `for(initialization; condition; increment)`
Un bucle con una `initialization`, una `condition` y un `increment` definidos.
10. `break`
Termina el bucle o switch actual.
15. `#include <file>`
Incluye un archivo de cabecera o biblioteca en el programa. `<file>` es el nombre del archivo de cabecera o biblioteca.
1. `strlen(str)`
Devuelve la longitud de una cadena `str`.
4. `strcmp(str1, str2)`
Compara las cadenas `str1` y `str2`. Devuelve 0 si son iguales, un número negativo si `str1` es menor que `str2`, y un número positivo si `str1` es mayor que `str2`.
7. `sprintf(str, format, ...)`
Escribe datos formateados a la cadena `str`. `format` es una cadena que contiene texto y especificadores de formato.
8. `sscanf(str, format, ...)`
Lee datos formateados de la cadena `str`. `format` es una cadena que contiene especificadores de formato.
9. `malloc(size)`
Asigna `size` bytes de memoria dinámicamente y devuelve un puntero a la memoria asignada.
11. `realloc(ptr, new_size)`
Cambia el tamaño de la memoria asignada apuntada por `ptr` a `new_size` bytes.
12. `free(ptr)`
Libera la memoria asignada apuntada por `ptr`.
13. `exit(status)`
Termina la ejecución del programa con un estado de salida `status`.
14. `atof(str)`
Convierte la cadena `str` a un número de punto flotante.
15. `atoi(str)`
Convierte la cadena `str` a un entero.
16. `atol(str)`
Convierte la cadena `str` a un entero largo.
17. `rand()`
Genera un número aleatorio entre 0 y RAND_MAX.

## Para files
1. `open(path, flags, mode)`
Abre el archivo ubicado en `path` con las `flags` especificadas (`O_RDONLY` para lectura, `O_WRONLY` para escritura, `O_RDWR` para lectura y escritura, `O_CREAT` para crear el archivo si no existe, etc. \[hay ejemplos en los archivos de clase\]). `mode` especifica los permisos del archivo si se crea uno nuevo (como `S_IRUSR | S_IWUSR` para lectura y escritura del propietario). Devuelve un file descriptor o -1 si ocurre un error.
2. `write(fd, buf, count)`
Escribe `count` bytes desde el buffer `buf` al archivo representado por el descriptor de archivo `fd`. Devuelve el número de bytes escritos o -1 si ocurre un error.
3. `lseek(fd, offset, whence)`
Cambia la posición del descriptor de archivo `fd` al `offset` especificado. `whence` puede ser `SEEK_SET` para establecer la posición en `offset` bytes desde el principio del archivo, `SEEK_CUR` para establecer la posición en `offset` bytes desde la posición actual, o `SEEK_END` para establecer la posición en `offset` bytes desde el final del archivo. Devuelve la nueva posición o -1 si ocurre un error.

## Ejemplo de codigo:
```
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>
#include <unistd.h>
#include <stdio.h>

int main(int argc, char **argv){
	int fd, len, i, max, pos;
	char c, tmp='X';

	fd = open(argv[1], O_RDWR);
	if (fd < 0){
		perror("Error en open");
		return 1;
	}
	len = lseek(fd, 0, SEEK_END);
	lseek(fd, len/2, SEEK_SET);

	while (read(fd, &c, 1) > 0){
		lseek(fd, -1, SEEK_CUR);
		write(fd, &tmp, 1);
		tmp = c;
		pos = lseek(fd, 0, SEEK_CUR);
		printf("Pos %d\n", pos);
	}
	write(fd, &tmp, 1);

	close(fd);

	return 0;
}
```
