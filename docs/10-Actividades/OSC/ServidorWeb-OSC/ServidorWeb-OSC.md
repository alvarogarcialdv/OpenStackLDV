# Servidor Web-OSC

En esta actividad debes, usando *OpenStack Client*, realizar una configuración donde se integren las configuraciones de las actividades anteriores, 


- Borra **todas las configuraciones realizadas en las explicaciones de clase y en las prácticas anteriores**, asegúrate de haber hecho la actividad [Borrado de componentes](../../../10-Actividades/Horizon/Borrado/Borrado.md).
- Verifica la topología de red del proyecto.
- Crea una **nueva red IP** (**red-asirXX**) con el direccionamiento **172.16.XX.0/24**.
  - **Gateway**: **172.16.XX.1**
  - **Servidor DHCP** que asigne la siguiente configuración.
    - Rango **172.16.XX.10, 172.16.XX.30**.
    - DNS: **8.8.8.8**.
- Crea un **nuevo Router** (**router-asirXX**) que conecte la red creara con la red **Provider (red del instituto).**
- Crea un **nuevo par de claves SSH.**
- Crea una nueva instancia (con el nombre **panoramixXX**) a partir de la imagen del sistema operativo **debian11** con **el sabor m1.small**. Asegurare de que se se conecta **a la red que has creado**  y que **se  inyecta la clave pública SSH** que has creado.
- **Asocia una IP flotante** a la instancia.
- Crear un **nuevo grupo de seguridad** con el nombre **gruposeguridadXX** .  Crea las reglas necesarias para **permitir el tráfico IMCP** y el **tráfico SSH (22/TCP)** de entrada a las instancias que pertenezcan al grupo.
- Sobre la instancia que has creado, **quita el grupo de seguridad default y asígnale el nuevo grupo de seguridad.**
- Desde tu equipo **haz ping la ip flotante** asignada a la instancia y **establece una conexión por SSH.**
- Verifica que hay **conexión desde la instancia con Internet y que resuelve nombres DNS.**
- Instala el **servidor apache** en la instancia.
- Realiza las configuraciones adecuadas para que puedes conectarte al servidor Apache desde el navegador de tu equipo.

