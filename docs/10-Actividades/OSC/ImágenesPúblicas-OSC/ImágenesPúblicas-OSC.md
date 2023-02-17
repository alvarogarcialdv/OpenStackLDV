# Imágenes públicas-OSC
## Introducción
En está actividad vamos a consultar las imágenes públicas disponibles en **OpenStackLDV** usando *OpenStack Client*.

Recuerda que una imagen es un sistema preconfigurado que se utiliza como base para crear instancias (máquinas virtuales). Cada imagen es un fichero que contiene la estructura y contenidos completos de un dispositivo de almacenamiento (HDD, CD, DVD, etc.).

Puedes consultar más información sobre **imágenes** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#Imágenes). 

Lo habitual en un IaaS es que existan un conjunto de imágenes genéricas (*cloud-images*) y públicas (accesibles por todos los usuarios) para poder crear instancias.

## Configuración

Configura tu entorno para poder acceder a tu proyecto usando *OpenStack Client* tal y como se explica en la actividad [Instalación y configuración inicial de OpenStack Client (OSC)](../../../10-Actividades//OSC/ImágenesPúblicas-OSC/ImágenesPúblicas-OSC.md#Configuración).

Consulta las imágenes y observa las imágenes públicas disponibles.

```
(osc) openstack image list
```

Consulta una de ellas, puedes usar su id o su nombre, y observa sus características.
````
(osc) openstack image show 646a3e52-848d-4e8e-bcec-509022fa5b4b
(osc) openstack image show LDV-cirros0.5.2-x86_64
````

