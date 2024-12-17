# Coursera-module-3-GIT
Practice account for learning Git

Conectarse a GitHub a través de HTTPS
Cuando se utiliza Github a través de la plataforma Coursera, es necesario autenticarse utilizando un Token de Acceso Personal a través de HTTPS. El token de acceso personal es una contraseña especial que se utiliza en lugar de la contraseña real de la cuenta. Cuando haya terminado de utilizar el token, puede revocarlo para que no pueda volver a utilizarse. También es posible establecer un tiempo de caducidad para el token. Esto ayuda a mantener la seguridad de su cuenta.

Generar un token de acceso personal
Ahora debemos configurar nuestro token de acceso personal.

Paso 1: Acceda a Github

Paso 2: Pulse el icono del perfil en la parte superior derecha de la pantalla y seleccione Settings (Configuración).

Click on settings. 
Paso 3: En la pantalla Settings (Configuración), en el lado izquierdo, haga clic en Developer Settings (Configuración del desarrollador).

Click on Developers Settings. 
Paso 4: En la pantalla Developer Settings (Configuración del desarrollador), haga clic en Personal Access Tokens (Tokens de acceso personal) y luego en Generate Token (Generar token).

Click on Personal Access Token and then Generate Token. 
Paso 5: En la página Nuevo token de acceso personal, introduzca un nombre de token y un tiempo de caducidad. Si desea revocar manualmente el token, establezca el tiempo de caducidad como No expiration (Sin caducidad).

Enter token name and expiry time. 
Paso 6: En Scopes (Ámbitos), seleccione repo.

Select repo. 
Paso 7: Desplácese hasta el final de la página y haga clic en Generate Token (Generar token).

Click on generate token. 
Paso 8: Ahora se genera el token. Asegúrese de copiar y anotar el token, ya que se ocultará al salir de la página. Este token se puede utilizar ahora cuando se conecta a un repositorio a través de HTTPS.

Copy and save the token. 
Nota: Si pierde el token, puede borrar el antiguo y crear uno nuevo.

Acceso a los repositorios
Cuando acceda a un repositorio y utilice la autenticación HTTPS, asegúrese de utilizar siempre la dirección HTTPS del repositorio.

Use the HTTPS address of the repository. 

Conectarse a GitHub a través de SSH
Si planea usar Github desde su dispositivo local, la forma recomendada de autenticarse es usando Secure Shell, o SSH para abreviar. Esto requiere la creación de dos claves: una clave pública y otra privada. La ventaja de usar SSH es que no necesita introducir sus credenciales cuando interactúa con el repositorio remoto. Las claves se generan y almacenan en su máquina local y luego la clave pública se copia en el servidor de Github. Una vez terminada la configuración, todas las operaciones se autentificarán utilizando las claves.

Generar claves SSH
El proceso es el mismo tanto para Windows como para Mac. En Windows, puede utilizar la terminal Git Bash y en Mac, la terminal estándar funcionará.

Abra la terminal

Introduzca lo siguiente: 
ssh-keygen -t ed25519 -C "your@email.com"

Sustituya el correo electrónico por el suyo y pulse Intro.

Se le pedirá que introduzca una contraseña. Pulse Intro para omitir el colocar la contraseña y lo mismo para omitir colocar la contraseña de nuevo. 

Generating public/private ed25519 key pair.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in ./ssh/private_key.
Your public key has been saved in ./ssh/public_key.pub.
The key fingerprint is:
SHA256:UDQI5N1FL3QSq7Gj1o12mkr9Me7qGMZAeE1s9BWIln4 your@email.com
The key's randomart image is:
+--[ED25519 256]--+
|   .o+o=+oOo.    |
|   o +B+.= =     |
|  . +++ + o .    |
|   o  ..E+ .     |
|    .  .S        |
|     o + +       |
|      B = =      |
|     + + * o     |
|      oo=o+      |
+----[SHA256]-----+

Una vez que haya confirmado se generará lo anterior para confirmar que las claves fueron creadas.

Ambas claves se guardarán en la carpeta .ssh.

Para añadir nuestra clave a Github, necesitamos obtener una copia de la clave pública que siempre se identifica como .pub en su directorio local. 

Encuentre el nombre del archivo de claves utilizando el siguiente comando. 
ls ~/.ssh/
A continuación, utilice el siguiente comando para copiar el archivo, sustituyendo <SU CLAVE> por el nombre del archivo de claves de su dispositivo. 
pbcopy < ~/.ssh/<YOUR KEY>.pub o en windows con la terminal bash de GIT cat ~/.ssh/id_ed25519.pub 
Esto generará la clave pública

Añadir sus claves a Github
Ahora tenemos que añadir nuestra clave pública a Github para dar acceso a los repositorios que creemos.

Paso 1: Inicie sesión en Github

Paso 2: Pulse el icono del perfil en la parte superior derecha de la pantalla y seleccione Settings (Configuración).

Click on settings. 
Paso 3: En la pantalla Settings (Configuración), en el lado izquierdo, en la sección de acceso, haga clic en SSH and GPG Keys (Claves SSH y GPG)

Click on SSH and GPG Keys button
Paso 4: Haga clic en el botón New SSH key (Nueva clave SSH) en verde en la parte derecha de la pantalla.

Click on New SSH key button
Paso 5: Introduzca un título y pegue la clave pública que copió anteriormente.

Enter title and paste pubic key
Paso 6: Haga clic en el botón Add SSH key (Añadir clave SSH).

Ahora puede acceder a Github a través de SSH.

Acceso a los repositorios
Cuando acceda a un repositorio y utilice la autenticación SSH, asegúrese de utilizar siempre la dirección SSH del repositorio.

Always use the SSH address of the repository
