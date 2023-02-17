# Redes y routers
## Introducción
En está actividad vamos crear una **red** con direccionamiento **10.33.1.0/24** (**subred** en terminología de OpenStack) y un **router** que conectará la red creada con la red del instituto (192.168.0.0/16) (red **provider** en terminología de **OpenStackLDV**).

Consulta información sobre **redes, subredes y routers** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#redes-y-dispositivos-de-red).
## Configuración
### Redes y subredes

Accede a Horizon e Inicia sesión con tu usuario y contraseña.

En el menú de la izquierda accede a ***Project, Network, Networks*** y observa que existe la red **provider**. Esta red representa a la red del instituto y es accesible desde todos los proyectos de **OpenStackLDV**. No es posible conectar directamente instancias a esta red, si se intenta crear una instancia conectada a está red se provocará un error y la instancia no se creará correctamente.
![Red provider](img/provider.png)

Accede a ***Project, Network, Routers*** y verifica que no existe ningún router en tu proyecto.

Accede a ***Project, Network, Network Topology*** y observa el diagrama con las redes y routers actuales. Solo existirá la red **provider**.
![Topología de red inicial](img/topología_inicial.png)

Accede ***Project, Network, Networks***.

- Pincha en ***Create Networks*** para crear una nueva red y una nueva subred.

- Introduce el nombre **red01** y pincha en ***Next***.

![Red](img/red01.png)

- Introduce el nombre **subred01**, dirección de red **10.33.1.0/24**, gateway **10.33.1.1**, y pincha en ***Next***.

![Red](img/subred01.png)

- Habilita un **servidor DHCP** en la red que sirva en el rango **10.33.1.10, 10.33.1.30** y otorgue **8.8.8.8 como servidor DNS**. Pincha en ***Create*** para crear la red.

![Servidor DHCP](img/dhcp01.png)

![Red creada](img/red01_creada.png)

Accede a ***Project, Network, Network Topology*** y observa el diagrama con las redes y routers actuales. Existiran las dos redes pero no están conectadas.
![Topología con red01](img/topología_red01creada.png)

### Routers

Accede ***Project, Network, Routers***. Pincha en ***Create Routers*** para crear un nuevo router. Asígnale el nombre **router01** y selecciona ***provider*** como red externa. Pincha en ***Create*** para crear el router.
![Router01](img/router01.png)

Accede a ***Project, Network, Network Topology***  y verifica la topología de red. Observa que el router solo está conectado a la red ***provider***.
![Topología con router01](img/topología_router01creado.png)

Accede ***Project, Network, Routers*** y pincha sobre el **router01**.

Accede a la pestaña ***Interfaces*** y pincha en ***Add interface***.

- Selecciona la **red01** y introduce la IP **10.33.1.1**.

![Interfaz del router01](img/interface.png)

- Pincha en ***Submit*** para crear el interfaz.

Accede a ***Project, Network, Network Topology***  y verifica la topología de red. Observa que se ha creado un interfaz en el router y se ha conectado con la **red01**. Fíjate en la IP que se le ha asignado al interfaz.
![Topología completa](img/topología_completa.png)