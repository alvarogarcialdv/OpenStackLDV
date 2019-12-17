# P08-Borrado

En esta práctica vamos a borrar los elementos creados en las pŕacticas anteriores:

- Borrar el volumen.
- Borrar el snapshot.
- Borra las instancias.
- Borrar el par de claves SSH.
- Borrar la red y el router.
- Borrar las reglas creadas en el grupo de seguridad *default*.
- Liberar las IPs flotantes reservadas.

El objetivo es dejar el proyeco tal y como estaba antes de realizar las prácticas.

1. Accede a Horizon.
2. Inicia sesión con tu usuario y contraseña.
3. Accede a  ***Project, Volumes, Volumes***.
4. Sobre el volumen **vol01** en la columna ***Actions***  accede a ***Manage Attachements*** y desasocia el volumen de la instancia **cirros034**.
5. Selecciona el volumen **vol01**  y pincha en ***Delete volumen*** para borrarlo.
6. Accede a ***Project, Compute, Images***.
7. Selecciona la snapshot **cirros03-sn01** y pincha en ***Delete Image***.
8. Accede a ***Project, Compute, Instances***.
9. Selecciona las cuatro instancias y pincha en ***Delete Instances***.
10. Accede a ***Project, Compute, Key Pairs***.
11. Selecciona el par de claves y pincha en ***Delete Key Pairs***.
12. Accede a ***Project, Network, Routers***.
13. Selecciona el el router **router01** y pincha en ***Delete Routers***.
14. Accede a ***Project, Network, Networks***.
15. Selecciona la red **red01** y pincha en ***Delete Networks***.
16. Accede a ***Project, Network, Security Groups***.
17. Sobre el grupo ***default*** pincha en ***Manage Rules***. Borras la regla de ICMP y SSH.
18. Accede a ***Project, Compute, Network, Floating IPs***.
19. Selecciona las dos IPs flotantes y pincha en ***Release Floating IPs***.
20. Accede a  ***Project, Compute, Overview*** y observa que están todos los recursos disponibles.

