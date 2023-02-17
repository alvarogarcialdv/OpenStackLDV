# Borrado
## Introducción
En esta actividad vamos a borrar los elementos creados en las pŕacticas anteriores:

- Borrar el volumen.
- Borrar el snapshot.
- Borra las instancias.
- Borrar el par de claves SSH.
- Borrar la red y el router.
- Borrar las reglas creadas en el grupo de seguridad *default*.
- Liberar las IPs flotantes reservadas.

El objetivo es dejar el proyeco tal y como estaba antes de realizar las actividads.
## Configuración
Accede a Horizon e Inicia sesión con tu usuario y contraseña.

Accede a  ***Project, Volumes, Volumes***.

- Sobre el volumen **vol01** en la columna ***Actions***  accede a ***Manage Attachements*** y desasocia el volumen de la instancia **cirros03**.

- Selecciona el volumen **vol01**  y pincha en ***Delete volumen*** para borrarlo.

Accede a ***Project, Compute, Images***.

- Selecciona la snapshot **cirros03-sn01** y pincha en ***Delete Image***.

Accede a ***Project, Compute, Instances***.

- Selecciona las cuatro instancias y pincha en ***Delete Instances***.

Accede a ***Project, Compute, Key Pairs***.

- Selecciona el par de claves y pincha en ***Delete Key Pairs***.

Accede a ***Project, Network, Routers***.

- Selecciona el el router **router01** y pincha en ***Delete Routers***.

Accede a ***Project, Network, Networks***.

- Selecciona la red **red01** y pincha en ***Delete Networks***.

Accede a ***Project, Network, Security Groups***.

- Sobre el grupo ***default*** pincha en ***Manage Rules***. Borras la regla de ICMP y SSH.

Accede a ***Project, Compute, Network, Floating IPs***.

- Selecciona las dos IPs flotantes y pincha en ***Release Floating IPs***.

Accede a  ***Project, Compute, Overview*** y observa que están todos los recursos disponibles.

