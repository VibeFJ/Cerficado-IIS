<h1 align="center">Instrucciones para certificado IIS ✅</h1>
<h3 align="center">GoDaddy 👌</h3>

Identificar Archivos. 🔍

- generated-csr.txt
- generated-private-key.txt

CARPETA SSL 📂

- certificado.crt
- certificado.pem
- intermediates.p7b

Ejecutable openssl.exe instalado 🌐

En caso de contar con xamp hay una versión que sirve en la carpeta (xampp\php\extras\openssl)✴️

Los archivos ponerlos en una carpeta accesible.
O igual puedes ponerlos en una carpeta en el Disco C

**EJEMPLO**
<br>
**C:\Certificados** 📜

Limpiar los archivos, los archivos descargados pueden traer caracteres especiales que no son visibles,
lo recomendable es limpiarlos creando un nuevo archivo txt copiar y pegar el texto en un nuevo txt
y cambiar el formato ya sea la private-key o el archivo crt

Al crear el archivo de texto nuevo escribir manualmente las cabeceras

**LIMPIAR ARCHIVO .CRT**

-----BEGIN CERTIFICATE-----
<br>
//Contenido del archivo crt
<br>
-----END CERTIFICATE-----
<br>

 - Guardar con la extensión .crt

**LIMPIAR LLAVE PRIVADA**
<br>
-----BEGIN PRIVATE KEY-----
<br>
//Contenido del archivo key
<br>
-----END PRIVATE KEY-----

 - Guardar con la extensión .key
 - Una vez que ambos archivos estan limpios ejecutar el comnado para crear el archivo .pfx

Usar el siguiente comando

C:\xampp\apache\bin\openssl.exe pkcs12 -export -out C:\Certificados\certificado.pfx -inkey C:\Certificados\server.key -in C:\Certificados\server.crt

Pedira una contraseña para proteger el archivo
Contraseña: Contra05

y la confimación de la contraseña

Contraseña: Contra05

De esta forma ya esta el archivo pfx correcto con el certificado y la llave privada unidos.

<h1 align="center">Agregar certificado a sitio web en IIS ✅</h1>

- Win + R
- Escribir mmc y dar en Ejeutar.
- Archivo -> Agregar o quitar complemento.
- Agregar el complemento de Certificados con (Cuenta de equipo).
- El equipo es (Equipo Local).
- Despues en Finalizar y Aceptar

<h3 align="center">Certificado 👌</h3>

- En Certificados -> Personal -> Certificados click derecho y en Todas las tareas -> Importar
- En Equipo Local siguiente y se selecciona el archivo pfx.
- Siguiente y se ingresa la contraseña ingresada para el archivo.
- Contraseña: Contra05
- Seleccionar que los certificados sean en Personal y Finalizar

<h3 align="center">Renombrar 🖋️</h3>

- En los Certificados se selecciona el certificado, click derecho -> propiedades y Nombre descriptivo, se puede agregar el nombre para reconocerlo ya que sale con el predeterminado.
- Damos en Aplicar y Aceptar
- Ahora en el administrador de IIS, Win + R y escribimos **inetmgr** y damos click en Aceptar
- En certificados del Servidor ya aparecera nuestro certificado.
- Para agregar al sitio web, seleccionamos el sitio, en enlaces o **(bindings)**
- Agregamos uno nuevo con el Tipo https con el puerto 443.

<h3 align="center">Nombre del Host 💫</h3>

- El nombre del host es el del dominio completo es decir **(tusitio.web.com)**
- Seleccionamos en Requerir indicación del nombre de servidor **(En caso de tener más sitios en el mismo servidor)** y debes de configurar **(el resto de sitios de la misma forma)**.
- Selecciona el Certificado SSL y damos en aceptar.

<h3 align="center">El sitio web ya cuenta con el certificado SSL de seguridad. 🌐</h3>






