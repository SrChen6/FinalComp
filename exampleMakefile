all: encript encript_v2 encript_v3

encript: encriptador.c
	gcc -o encript encriptador.c

encript_v2: v2/encriptador_v2.c v2/key.c v2/key.h	
	gcc -o v2/encript_v2 v2/encriptador_v2.c v2/key.c
	
encript_v3: v3/encriptador_v3.c	
	gcc -o v3/encript_v3 v3/encriptador_v3.c
	
clean:
	rm encript v2/encript_v2 v3/encript_v3
