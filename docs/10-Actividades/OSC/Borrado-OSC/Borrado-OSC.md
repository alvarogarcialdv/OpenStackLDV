# Borrado-OSC
## Introducción
En esta actividad, , usando *OpenStack Client*,  vamos a borrar los elementos creados en las pŕacticas anteriores:

- Borrar el volumen.
- Borrar el snapshot.
- Borra las instancias.
- Borrar el par de claves SSH.
- Borrar la red y el router.
- Borrar las reglas creadas en el grupo de seguridad *default*.
- Liberar las IPs flotantes reservadas.

El objetivo es dejar el proyeco tal y como estaba antes de realizar las actividads.
## Configuración
Configura tu entorno para poder acceder a tu proyecto usando *OpenStack Client* tal y como se explica en la actividad [Instalación y configuración inicial de OpenStack Client (OSC)](../../../10-Actividades//OSC/ImágenesPúblicas-OSC/ImágenesPúblicas-OSC.md#Configuración).

Consulta los volumenes disponibles.

```
(osc)openstack volume list
```

- Desasocia el volumen **vol1** de la instancia **cirros04**.

```
(osc)openstack server remove volume cirros04 vol1
```

- Borra el volumen **vol1**.

```
(osc)openstack volume delete vol1
(osc)openstack volume list
```

Consulta las instancia disponibles

```
(osc)openstack server list
```

- Borra la 4 instancias

```
(osc)openstack server delete asterix01
(osc)openstack server delete debian01
(osc)openstack server delete cirros03
(osc)openstack server delete cirros04
```

Consulta las imágenes dispoibles.

```
(osc)openstack image list
```

- Borra la snapshot **cirros03-sn1** 

```
(osc)openstack image delete cirros03-sn1
```

Consulta los pares de claves.

```
(osc)openstack key list
```

- Borra el par de claves.

```
(osc)openstack key delete ssh01
```

Consulta los routers.

```
(osc)openstack router list
```

- Consulta la información del **router01**.

```
(osc)openstack router show router01
```

- Borra el puerto asiciado al interaz con IP 10.33.1.1

```
openstack router remove port router01 5ee21dc8-c356-40ab-bf83-7fe345f59942
```

- Borra el **router01**.

```
(osc)openstack router delete router01
(osc)openstack router list
```

Consulta las redes.

```
(osc)openstack network list
```

- Borra la **red01**.

```
(osc)openstack network delete red01
(osc)openstack network list
```

Consulta las reglas del grupo de seguridad **default**.

```
(osc) openstack security group rule list default
```

- * Borra la regla de ICMP y SSH.

```
(osc) openstack security group rule delete cd21dacd-916a-4e9b-9fb1-8ce48c82eca6
(osc) openstack security group rule delete cd21dacd-916a-4e9b-9fb1-8ce48c82eca6
(osc) openstack security group rule list default
```

Consulta las IPs flotantes.

```
(osc)openstack floating ip list
```

- Libera las IPs flotantes.

```
(osc)openstack floating ip delete 192.168.211.183
(osc)openstack floating ip delete 192.168.211.75
```

