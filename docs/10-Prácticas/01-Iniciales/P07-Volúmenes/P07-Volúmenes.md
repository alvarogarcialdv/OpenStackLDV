# P07-Volúmenes

En esta práctica vamos a:

- Crear un volumen de 1GB.
- Asociar el volumen a una instancia que ya está creada.
- Iniciar sesión en la instancia, crear una partición, formatéarla, móntarla y creat un par de ficheros.
- Desasociar el volumen de la instancia y asociarlo a otra instancia.

Consulta información sobre **almacenamiento** y **volúmenes** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#almacenamiento).

1. Accede a Horizon.
2. Inicia sesión con tu usuario y contraseña.
3. Accede a  ***Project, Volumes, Volumes***.
4. Pincha en ***Create Volume*** y crea un volumen **vacío** con el nombre **vol1** de **1GB**.
![Crear volumen](img/vol01_1.png)
5. Sobre el volumen credo en la columna ***Actions***  accede a ***Manage Attachements*** y asocia el volumen a la instancia **cirros03**.
![Asociar el volumen a una instancia](img/vol01_2.png)
6. Observa el nombre de dispositivo con el que se ha añadido el volumen a la máquina (en este caso /dev/vdb).
![Volumen asociado a una instancia](img/vol01_3.png)
7. Abre un terminal y establece una conexión SSH con la instancia **cirros03**.
8. Crea una partición, formatéala, móntala y crea un par de ficheros.

	`sudo fdisk -l`

	`sudo fdisk /dev/vdb`

	`n`

	`p`

	`1`

	`Valor por defecto (2048)`

	`Valor por defecto`

	`w`

	`sudo mkfs.ext4 /dev/vdb1`

	`sudo mkdir /mnt/data`

	`sudo mount /dev/vdb1 /mnt/data`

	`cd /mnt/data`

	`sudo touch hola.txt`

	`sudo touch adios.txt`

9. Sobre el volumen credo en la columna ***Actions***  accede a ***Manage Attachements*** y desasocia el volumen de la instancia **cirros03**.
10. Sobre el volumen credo en la columna ***Actions***  accede a ***Manage Attachements*** y asocia el volumen a la instancia **cirros04**.
11. Inicia sesión en **cirros04**, monta el volumen y verifica que los dos ficheros están creados.

	`bash`

	`sudo mkdir /mnt/data`

	`sudo mount /dev/vdb1 /mnt/data`

	`ls`

12. Apaga las instancias **cirros03** y **cirros04**.