1. Selecciona un documento pdf y encríptalo y fírmalo (opción --sign). Envíalo a un compañero, que debe, en primer lugar, verificar la firma y posteriormente descifrar el documento.

~~~
$ gpg --sign Servidor\ de\ instalación.pdf 
$ scp Servidor\ de\ instalación.pdf.gpg ftirado@172.22.6.25:
~~~

Para verificar la firma se utiliza la opción:

~~~
$ gpg --verify ExFH-2TR.pdf.gpg 
gpg: Firmado el mar 08 oct 2019 11:07:01 CEST
gpg:                usando RSA clave A615146E82E272C899A34100F405106DBBABFB72
gpg: Firma correcta de "Fernando Tirado <fernando.tb.95@gmail.com>" [desconocido]
gpg: ATENCIÓN: ¡Esta clave no está certificada por una firma de confianza!
gpg:          No hay indicios de que la firma pertenezca al propietario.
Huellas dactilares de la clave primaria: A615 146E 82E2 72C8 99A3  4100 F405 106D BBAB FB72
~~~

Desencriptamos:

~~~
$ gpg --output ExFH-2TR.pdf --decrypt ExFH-2TR.pdf.gpg 
gpg: Firmado el mar 08 oct 2019 11:07:01 CEST
gpg:                usando RSA clave A615146E82E272C899A34100F405106DBBABFB72
gpg: Firma correcta de "Fernando Tirado <fernando.tb.95@gmail.com>" [desconocido]
gpg: ATENCIÓN: ¡Esta clave no está certificada por una firma de confianza!
gpg:          No hay indicios de que la firma pertenezca al propietario.
Huellas dactilares de la clave primaria: A615 146E 82E2 72C8 99A3  4100 F405 106D BBAB FB72
~~~


2. Realiza el mismo ejercicio pero obteniendo una firma ASCII.
~~~
$ gpg --export -a Paloma R. Garcia Campon > PalomaR.Garcia.asc
~~~

~~~
$ gpg --sign ExFH-2TR.pdf 
$ scp Servidor\ de\ instalación.pdf.gpg ftirado@172.22.6.25:

$ scp clave-publica.asc moralg@172.22.9.198:
$ scp ExFH-2TR.pdf.gpg moralg@172.22.9.198:



