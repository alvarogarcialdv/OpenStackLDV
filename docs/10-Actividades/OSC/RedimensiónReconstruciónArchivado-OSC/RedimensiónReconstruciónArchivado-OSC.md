# Redimensión, reconstrución y archivado de instancias-OSC
## Introducción

En esta actividad, usando *OpenStack Client*, vamos a:

- Redimensionar una instancia existente cambiando su sabor.
- Reconstruir una instancia existente.
- Archivar una instancia para liberar sus recursos.


Consulta información sobre **redimensionar** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#redimensionar-una-instancia).

Consulta información sobre **reconstruir** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#reconstruir-una-instancia).

Consulta información sobre **Archivar** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#archivar-una-instancia).


## Configuración

Configura tu entorno para poder acceder a tu proyecto usando *OpenStack Client* tal y como se explica en la actividad [Instalación y configuración inicial de OpenStack Client (OSC)](../../../10-Actividades//OSC/ImágenesPúblicas-OSC/ImágenesPúblicas-OSC.md#Configuración).

### Redimensionar una instancia

Redimensiona la instancia  **cirros02** usando como nuevo sabor **m1.small**.

```
(osc) openstack server resize --flavor m1.small cirros02
```

En este momento OpenStack esta verificando si es posible llevarlo a cabo.  Si es posible la instancia pasa al estado VERIFY_RESIZE  y tenemos que Confirmar la redimensión o Revertir la redimensión.

```
(osc) openstack server list
(osc) openstack server show cirros02
```

Espera a que el valor  `OS-EXT-STS:vm_state`    tenga el valor  `resized`.

Confirma la redimensión y observa como el sabor ha cambiado.

```
(osc) openstack server resize confirm cirros02
(osc) openstack server list
(osc) openstack server show cirros02
```

### Reconstruir una instancia

Reconstruye la instancia **cirros02** usandp como nueva imagen **LDV-debian11**.

```
(osc)openstack image list
(osc)openstack server rebuild --image LDV-debian11-x86_64  cirros02
(osc)openstack server list
```

Observa como cambia la imagen de la instancia.

Cambia el nombre de la instancia a **debian01**.

```
(osc)openstack server set --name debian01 cirros02
(osc)openstack server list
```

### Archivar una instancia

Archiva la instancia **debian01**. 

```
(osc)openstack server shelve debian01
(osc)openstack server list
(osc)openstack server show debian01
```

Espera a que termine el proceso y la instancia pase a estado **SHELVED_OFFLOADED**.

Onserva que se ha creado una ***snapshot*** de la instancia.

```
(osc)openstack image list
```

Desarchiva la instancia.

```
(osc)openstack server unshelve debian01
```

Verifica el estado de la instancia es de nuevo ***Active*** y que se ha eliminado la ***snapshot***.

```
(osc)openstack server list
(osc)openstack server show debian01
(osc)openstack image list
```