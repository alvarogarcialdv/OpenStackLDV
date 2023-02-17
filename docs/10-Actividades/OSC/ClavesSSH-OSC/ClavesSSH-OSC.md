# Claves SSH-OSC
## Introducción
En esta actividad, usando *OpenStack Client*, vamos a:

- Crear un par de claves SSH y descargar la clave privada.
- Crear otra instancia similar a las que has creado en actividads anteriores e inyectar la clave pública del par de claves creado.
- Establecer una conexión SSH con la instancia autenticándose por clave pública.

Consulta información sobre **claves SSH** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#claves-ssh).

## Configuración

Configura tu entorno para poder acceder a tu proyecto usando *OpenStack Client* tal y como se explica en la actividad [Instalación y configuración inicial de OpenStack Client (OSC)](../../../10-Actividades//OSC/ImágenesPúblicas-OSC/ImágenesPúblicas-OSC.md#Configuración).

Consulta las claves ssh disponibles.

```
(osc) openstack keypair list
```

Crea un par de claves con el con el nombre **ssh01** y descarga la clave privada en tu equipo.

``` 
(osc)openstack keypair create ssh01 > ssh01.pem
```
Consulta las claves ssh disponibles.

```
(osc) openstack keypair list
```

Crea una nueva instancia con el nombre **cirros03** inyectando la clave pública del par de claves que has creado.

```
(osc) openstack server create --flavor m1.tiny --image LDV-cirros0.5.2-x86_64 --network red01 --key-name ssh01 cirros03
(osc) openstack server list
```

Asígnale una IP flotante a la instancia y verifica que existe la regla para permitir el acceso SSH en el grupo de seguridad *default*.

- Consulta las IPs flotantes asignadas al proyecto.

```
 (osc)openstack floating ip list
```

- Reserva una IPs flotante. Estás IPs en un cloud público serían direcciones de Internet. En nuestro caso son direcciones de la **red provider (192.16.0.0/16)**, la red del instituto.

```
 (osc)openstack floating ip create provider
 (osc)openstack floating ip list
```

- Asocia la IP flotante asignada a la instancia **cirros03**.

```
(osc)openstack server add floating ip cirros03 192.168.211.125
```

- Observa la IP asociada.

```
(osc)openstack server list
```

- Consulta los grupos de seguridad.

```
(osc) openstack security group list
```

- Consulta las reglas del grupo ***default***.

```
(osc) openstack security group rule list default
```

Abre un terminal en tu equipo y haz un ping a la IP flotante.

Copia la clave privada descargada en el directorio **.ssh** del directorio home de tu usuario (~./ssh).

Dale permisos restrictivos (600) a la clave privada.

```chmod 600 ~/ssh01.pem```

Establece la conexión SSH y observa que no se pide la contraseña.

 	ssh -i ~/ssh01.pem cirros@ipflotante

En el siguiente [enlace](https://creodias.eu/faq-openstack/-/asset_publisher/TpmSvaqp3CVd/content/how-to-access-vm-from-windows-putty-?inheritRedirect=true) purdes ver como conectarte usando Putty como cliente. 