# Redes y routers-OSC
## Introducción
En está actividad vamos crear una **red** con direccionamiento **10.33.1.0/24** (**subred** en terminología de OpenStack) y un **router** que conectará la red creada con la red del instituto (192.168.0.0/16) (red **provider** en terminología de **OpenStackLDV**), usando *OpenStack Client*.

Consulta información sobre **redes, subredes y routers** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#redes-y-dispositivos-de-red).

## Configuración
### Redes y subredes

Configura tu entorno para poder acceder a tu proyecto usando *OpenStack Client* tal y como se explica en la actividad [Instalación y configuración inicial de OpenStack Client (OSC)](../../../10-Actividades//OSC/ImágenesPúblicas-OSC/ImágenesPúblicas-OSC.md#Configuración).

Consulta las **redes disponibles**  y observa que existe la red **provider**. Esta red representa a la red del instituto y es accesible desde todos los proyectos de **OpenStackLDV**. No es posible conectar directamente instancias a esta red, si se intenta crear una instancia conectada a está red se provocará un error y la instancia no se creará correctamente.

```
(osc)openstack network list
```

Consulta los **routers**  disponibles y verifica que no existe ningún router en tu proyecto.

```
(osc)openstack router list
```

Crea una red con el nombre **red01**.

```
(osc)openstack network create red01
```

Consulta la red creada.

```
(osc)openstack network list
(osc)openstack network show red01
```

En la **red01** crear una subred con el nombre **subred01**, dirección de red **10.33.1.0/24**,  gateway **10.33.1.1**,  **servidor DHCP** en la red que sirva en el rango **10.33.1.10, 10.33.1.30** y otorgue **8.8.8.8 como servidor DNS**. 

```
(osc) openstack subnet create --network red01 --subnet-range 10.33.1.0/24 --gateway 10.33.1.1 --dhcp --allocation-pool start=10.33.1.10,end=10.33.1.30 --dns-nameserver 8.8.8.8 subred01
```

Consulta la subred creada.

```
(osc)openstack subnet list
(osc)openstack subnet show subred01
```

### Routers

Crea un nuevo  router con el nombre **router01** y selecciona ***provider*** como red externa.

```
(ocs) openstack router create router01
(ocs) openstack router set router01 --external-gateway provider

```

Consulta el router creado.

```
(ocs) openstack router list
(ocs) openstack router show router01
```

Añade un interfaz al router y conéctalo a la **subred01** con la ip **10.33.1.1**.

```
openstack router add subnet router01 subred01 ## Por decto le asigla la IP 10.33.1.1
```

Consulta el router creado y observa que se ha creado un nuevo puerto (interfaz) conectado a la subred indicada.









