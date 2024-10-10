# Explotacion_web_basica
El objetivo es practicar algunos de los conceptos sobre seguridad de sistemas
web y responder a las siguientes preguntas. Para realizar la práctica se utilizará la misma configuración utilizada
en el laboratorio anterior (escaneo de redes). En lo que sigue, asumimos que la máquina
Metaexploitable2 tiene dirección IP 192.168.56.10.
## Actividades
1. Desde la máquina Linux conectada a la red virtual, abra un navegador y conéctese a
http://192.168.56.10. Utilice las credenciales admin/password para entrar. Haga click en
“DVWA Security” y seleccione “Low”. Haga click en “Command Execution” y después en
“View Source”. No es necesario conocer en profundidad el lenguaje php para
comprender el funcionamiento del script. Busque las funciones y las sentencias en el
código y asegúrese de comprender el funcionamiento del mismo.
a. Describa qué vulnerabilidad está presente en este código e ilustre con un
ejemplo cómo puede explotarse.
b. Bonus: repita los pasos anteriores pero seleccionando “Medium” y “High” en el
“DVWA Security” flag.

2. Seleccione “SQL Injection” con “DVWA Security” fijado a “Low”. Analice el código fuente
y describa qué vulnerabilidad contiene.
a. Realice una consulta SQL básica para recuperar todas las tablas de la base de
datos MySQL (Pista: averigüe primero cómo se llama esto en MySQL.)
b. Usando la salida del paso anterior, localice la tabla que lista todos los usuarios y
averigüe todos los campos de la tabla para cada usuario.
c. Recupere el listado de usuarios y el hash de sus contraseñas.
d. Bonus: use John the Ripper para romper una contraseña (cree un archivo
llamado pw.tx con “username:hash”, sin comillas, y ejecute “john
--format=raw-MD5 pwd.txt”, con la configuración que crea más apropiada).
3. Haga click en “CSRF” con “DVWA Security” set to “Low” y compruebe cómo la
contraseña cambia (mire el método HTTP y cómo el nombre de usuario y la nueva
contraseña se envía). Anote esta información.
a. Abra una ventana de terminal y utilice curl para cambiar la contraseña de un
usuario arbitrario utilizando lo que ha aprendido usando la opción CSRF. ¿Es
posible hacerlo? ¿Por qué?
b. Haga click en “XSS Reflected”, inspeccione el código fuente, y averigüe cómo
explotarlo para recuperar la cookie de sesión (document.cookie).
c. Repita el paso 3.1 utilizando la cookie que ha robado para cambiar la
contraseña. ¿Funciona?
