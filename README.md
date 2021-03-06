<h1 align="center"> Bitacora Sistemas Operativos </h1>

## Bitácora de Comandos del Curso de Sistemas Operativos 
Universidad Latinoamericana de Ciencia y Tecnologia ULACIT 2022 :mortar_board:

I Cuatrimestre

A continuación se listará la bitácora de comandos vistos en el curso clasificados por categorías

# Ejecutar como superusuario :zap:

Para la ejecución de comandos que requieran privilegios de superusuario se requiere del comando `sudo`

Este se coloca antes de otros comandos para modificar el modo en que se ejecutan, indicandole que se poseen permisos para proceder.

Por ejemplo, para ver el estado del firewall en Ubuntu usamos el comando:

`ufw status`

Sin embargo, al hacerlo así nos dará error porque requiere que seamos root para ejecutarlo. Al agregarle 'sudo' al inicio de la siguiente manera:

`sudo ufw status`

Primero nos solicitará y nos dejará ejecutará el comando exitosamente.

## Pasar a modo root

Con el comando `sudo su` podemos pasar a usar el usuario root con solo digitar la contraseña de nuestro usuario sin necesidad de conocer la contraseña de root.

Este lo podemos usar con solo digitarlo en la consola:

`sudo su`

# Instalación de Programas :wrench:

Cuando necesitemos instalar algún programa en Linux por línea de comandos lo haremos a través de un gestor de paquetes.

Existe una variedad de gestores de paquetes con sus propios repositorios de paquetes (programas) que pueden variar de distribución a distribución.

Por ejemplo, para los sistemas basados en Debian se utiliza `apt`, para Arch Linux se usa `pacman` y en Fedora `yum`

Cada uno tiene sus propias particularidades y comandos específicos. Para el caso específico de Ubuntu tenemos las siguientes opciones:

Para el gestor de paquetes `apt` en Ubuntu podemos utilizar la version `apt` o `apt-get`. 
Aunque ambos comandos cumplent el mismo propósito, `apt` por lo general el más amigable con el usuario.

- `apt install nombre-paquete`: Instala el paquete que le indiquemos en `nombre-paquete`
  - `apt install nombre-paquete -y`: El parámetro `-y` le indica a la línea de comandos que responda "yes" a cualquier confirmación requerida en la instalación
  - `apt install ruta`: En lugar de descargar el paquete de internet, utiliza el archivo instalador ubicado en la ruta especificada. Ejemplo: `apt install Downloads/Chrome.deb`
  
- `apt update`: Actualiza la información más reciente de los paquetes que tenemos instalados descargándola de internet. 
Este comando debe utilizarse siempre antes de `apt upgrade`

- `apt upgrade`: Instala las versiones más recientes de los paquetes instalados. En el caso de `apt-get` no instala las dependencias necesarias, mientras `apt` sí.

- `apt search palabra-clave`: Busca paquetes cuyo nombre o funcionalidad coincidan con `palabra-clave`. 
También se puede usar `apt-cache search palabra-clave`, aunque puede brindar resultados menos precisos.

- `add-apt-repository nombre-repositorio`: 
Incluye en la lista de paquetes disponibles los contenidos en el repositorio digitado. 
Esto nos permite instalar paquetes que no estén almacenados en el repositorio por defecto de `apt`.
  - `sudo add-apt-repository nombre-repositorio -y`: 
  El parámetro `-y` le indica a la línea de comandos que responda "yes" a cualquier confirmación requerida en la instalación
  
- `apt remove`: Desinstala un paquete.

- `apt autoremove`: Desinstala los paquetes que fueron instalados como dependencias de otros paquetes y ya no son necesarios.

- `dpkg`: Ubuntu adicionalmente tiene instalado por defecto el gestor de paquetes de Debian, el cual nos permite manejar a bajo nivel los paquetes instalados en el sistema. Es menos amigable para el usuario que `apt`.

Es importante saber que para usar el comando `apt` son necesarios privilegios de administrador por lo que siempre debe ir después del comando `sudo` o ejecutarse como root.
