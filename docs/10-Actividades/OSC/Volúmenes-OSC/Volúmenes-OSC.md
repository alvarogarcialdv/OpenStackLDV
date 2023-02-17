# Volúmenes-OSC
## Introducción
En esta actividad, usando *OpenStack Client*,  vamos a:

- Crear un volumen de 1GB.
- Asociar el volumen a una instancia que ya está creada.
- Iniciar sesión en la instancia, crear una partición, formatéarla, móntarla y creat un par de ficheros.
- Desasociar el volumen de la instancia y asociarlo a otra instancia.

Consulta información sobre **almacenamiento** y **volúmenes** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#almacenamiento).

## Configuración

Configura tu entorno para poder acceder a tu proyecto usando *OpenStack Client* tal y como se explica en la actividad [Instalación y configuración inicial de OpenStack Client (OSC)](../../../10-Actividades//OSC/ImágenesPúblicas-OSC/ImágenesPúblicas-OSC.md#Configuración).

Consuta los volumenes disponibles.

```
(osc)openstack volume list
```

Crea un volumen **vacío** con el nombre **vol1** de **1GB**.

```
(osc)openstack volume create --size 1 vol1
(osc)openstack volume list
```

Asocia el volumen a la instancia **cirros03**.

```
(osc)openstack server add volume --device /dev/sdb cirros03 vol1
```

Observa el nombre de dispositivo con el que se ha añadido el volumen a la máquina (en este caso /dev/vdb).

```
(osc)openstack server list
(osc)openstack volume list
```

Abre un terminal y establece una conexión SSH con la instancia **cirros03**.

Crea una partición, formatéala, móntala y crea un par de ficheros.
```
sudo fdisk -l
sudo fdisk /dev/vdb
n
p
1
Valor por defecto (2048)
Valor por defecto
w
sudo mkfs.ext4 /dev/vdb1
sudo mkdir /mnt/data
sudo mount /dev/vdb1 /mnt/data
cd /mnt/data
sudo touch hola.txt
sudo touch adios.txt
```
Desasocia el volumen de la instancia **cirros03**.

```
(osc)openstack server remove volume cirros03 vol1
(osc)openstack server list
(osc)openstack volume list
```

Asocia el volumen a la instancia **cirros04**.

```
(osc)openstack server add volume --device /dev/sdb cirros04 vol1
(osc)openstack server list
(osc)openstack volume list
```

Inicia sesión en **cirros04**, monta el volumen y verifica que los dos ficheros están creados.
``` 
bash
sudo mkdir /mnt/data
sudo mount /dev/vdb1 /mnt/data
ls
``` 
Apaga las instancias **cirros03** y **cirros04**.

```
(osc)openstack server stop cirros03
(osc)openstack server stop cirros04
```

