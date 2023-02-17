# Acciones básicas con instancias
## Introducción

En esta actividad vamos a probar a realizar algunas de las acciones que podemos hacer con una instancia.

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

Accede a Horizon e Inicia sesión con tu usuario y contraseña.

Accede a ***Compute, Instances*** y consulta las instancia disponibles. 

Sobre la instancia **cirros01** en la columna de la derecha despliega las posibles acciones que se pueden realizar con ella.

![image-20230207102730833](img/acciones.png)



Prueba a realizar las siguientes acciones.

- Edita la instancia y cambia el nombre a **asterix01**.
- Consulta el **log** de inicio de la instancia.
- Accede a la **Consola**.
- **Pausa** la instancia y observa su estado.
- **Reanuda** la instancia.
- **Suspende** la instancia y observa su estado.
- **Reanuda** la instancia.
- **Reinicia la instancia de forma ordenada**. Consulta el **log** de inicio.
- **Reinicia la instancia de forma forzosa**. Consulta el **log** de inicio.
- **Bloquea** y **desbloquea** la instancia.

Pincha sobre el nombre de la instancia y accede a la pestaña ***Actions Logs***. Podrás ver el registro de las diferentes acciones que has realizado.
