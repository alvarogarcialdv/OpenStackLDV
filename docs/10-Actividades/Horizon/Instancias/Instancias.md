# Crear instancias
## Introducción

En esta actividad vamos a:

- Crear una instancia en tu proyecto a partir de sabor ***tiny*** usando la imagen de **CirrOS**.
- Conectar la instancia a la **red01** creada en la actividad anterior.
- Usar la consola VNC para acceder la instancia creada y verificar su configuración IP.
- Crear otra instancia similar y verificar que hay comunicación IP entre las instancias.

Consulta información sobre **sabores** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#sabores-o-tipos-de-instancias).

Consulta información sobre **instancias** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#instancias).

## Configuración

Accede a Horizon e Inicia sesión con tu usuario y contraseña.

Accede a ***Project, Compute, Instances***. Pincha en ***Lauch Instance***.
- Introduce el nombre **cirros01** y pincha en ***Next***.

![Nombre de la instancia](img/cirros01_1.png)

- Selecciona la imágen pública de **CirrOS** para crear la instancia a partir de ella  y pincha en ***Next***.

![Imagen a partir de la que se crea  la instancia](img/cirros01_2.png)

 - Selecciona ***tiny*** como sabor y pincha en ***Next***.

![Sabor que determinará los recursos de la instancia](img/cirros01_3.png)

- Selecciona la **red01** para conectar a ella la instancia y pincha en ***Next***.

![Red a la que se conecta la instancia](img/cirros01_4.png)

- Pincha en ***Lauch Instance*** para crear la instancia (el resto de opciones disponibles se dejan com su valor por defecto, se tratarán en futuras actividads).

Observa las características de la instancia creada (imagen, sabor, estado, ...). Observa que la dirección IP asignada.
![Instancia creada](img/cirros01_5.png)

Accede a ***Project, Network, Network Topology*** y observa la topología de red. Observa donde está conectada la instancia.
![Topología de red](img/topología_1.png)

Accede a ***Project, Compute, Instances***. Pincha sobre el nombre de la instancia **cirros01** y accede a la pestaña ***Console***. Abre en nueva pestaña la consola usado el enlace ***Click here to show only console***.
![Consola](img/consola_1.png)

- Inicia sesión con el usuario **cirros** y la contraseña que indica **gocubsgo**.
- Consulta la IP de la máquina y verifica que tiene comunicación con la IP 10.33.1.1 (del router01).
  ![Consola](img/consola_2.png)

- Haz ping a una dirección a una IP del instituto (por ejemplo 192.168.200.100) y verifica que no hay comunicación.
- Usa ```nslookup``` para resolver un nombre DNS y verificar que hay comunicación con Internet ya que el servidor DNS al que se pregunta es el 8.8.8.8.
  ![Consola](img/consola_3.png)

Crea otra instancia similar con el nombre **cirros02** y verifica que hay comunicación IP entre las instancias. Tienes que seguir unos pasos simililares a los anteriores y verificar la IP de la nueva instancia.
![Instancia cirros02](img/cirros02.png)
![Consola](img/consola_4.png)

Accede a ***Project, Network, Network Topology*** y verifica la topología de red creada.
![Topología de red](img/topología_2.png)

En cada instancia accede a ***Actions*** (flecha hacía abajo), ***Shut Off Instance*** para apagar las instancias **cirros01** y **cirros02**.