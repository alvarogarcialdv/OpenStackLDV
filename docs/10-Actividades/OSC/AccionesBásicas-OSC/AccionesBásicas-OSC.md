# Acciones básicas con instancias-OSC
## Introducción

En esta actividad,  usando *OpenStack Client*, vamos a probar a realizar algunas de las acciones que podemos hacer con una instancia.

#### Acciones sobre a la información de la instancia

- ***Editar instancia***: Permite cambiar el nombre de la instancia.
- ***View log***: Permite  acceder al log de inicio de la instancia.
- ***Console***: Permite acceder a una  **consola VNC** para administrar la instancia.

#### Acciones sobre el ciclo de vida de la instancia

- ***Pause Instance***: Para la ejecución de la instancia guardando su estado en memoria RAM.
- ***Suspended Instance***: Para la ejecución de la instancia guardando su estado en memoria disco.
- ***Resume Instance***: Reaunda una instancia  suspendida o pausada.
- ***Shut Off Instance***: Apaga una instancia.
- ***Start Instance***: Inicia una instancia apagada.
- ***Soft Reboot***: envía una señal de reinicio al sistema operativo de la instancia.
- ***Hard Reboot***: fuerza el reinicio de la instancia. Solo deberíamos hacerlo si tenemos algún problema con ella.
- ***Lock Instance***:  Bloquea la instancia par que no se  pueda modificar su configuración.
- ***Unlock Instance***:  Desbloquea la instancia par que no se  pueda modificar su configuración. 

Puedes consultar información sobre todas las acciones a realizar en **Acciones con instancias** de la sección [Conceptos](../../../09-Conceptos/Conceptos.md#acciones- sobre- instancias).

## Configuración

Configura tu entorno para poder acceder a tu proyecto usando *OpenStack Client* tal y como se explica en la actividad [Instalación y configuración inicial de OpenStack Client (OSC)](../../../10-Actividades//OSC/ImágenesPúblicas-OSC/ImágenesPúblicas-OSC.md#Configuración).

Accede a ***Compute, Instances*** y consulta las instancia disponibles. 

```
(osc)openstack server list
```

Prueba a realizar las siguientes acciones sobre la instancia **cirros01**.

- Edita la instancia y cambia el nombre a **asterix01**.
```
(osc)openstack server set --name asterix01 cirros01
(osc)openstack server list
```
- Consulta el **log** de inicio de la instancia.

```
(osc)openstack console log show asterix01
```

- Accede a la **Consola**.
```
(osc)openstack console url show asterix01
Mostrara la URL para acceder a la consola
```

- **Pausa** la instancia y observa su estado.
```
(osc)openstack server pause asterix01
(osc)openstack server list
```

- **Reanuda** la instancia.
```
(osc)openstack server unpause asterix01
(osc)openstack server list
```

- **Suspende** la instancia y observa su estado.
```
(osc)openstack server suspend asterix01
(osc)openstack server list
```


- **Reanuda** la instancia.

```
(osc)openstack server resume asterix01
(osc)
```

- **Reinicia la instancia de forma ordenada**. Consulta el **log** de inicio.
```
(osc)openstack server reboot asterix01
(osc)openstack console log show asterix01
(osc)openstack server list
```

- **Reinicia la instancia de forma forzosa**. Consulta el **log** de inicio.
```
(osc)openstack server reboot --hard asterix01
(osc)openstack console log show asterix01
(osc)openstack server list
```

- **Bloquea** y **desbloquea** la instancia.

```
(osc)openstack server lock asterix01 
(osc)openstack server list
(osc)openstack server unlock asterix01 
```

Consulta el  ***Actions Logs***. Podrás ver el registro de las diferentes acciones que has realizado.
```
(osc)openstack server event list asterix01
```