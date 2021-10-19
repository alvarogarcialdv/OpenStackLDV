# P05-Claves SSH
En esta práctica vamos a:

- Crear un par de claves SSH y descargar la clave privada.
- Crear otra instancia similar a las que has creado en prácticas anteriores e inyectar la clave pública del par de claves creado.
- Establecer una conexión SSH con la instancia autenticándose por clave pública.

Consulta información sobre **claves SSH** en la sección [Conceptos](../../../09-Conceptos/Conceptos.md#claves-ssh).

1. Accede a Horizon.
2. Inicia sesión con tu usuario y contraseña.
3. Accede a  ***Project, Compute, Key Pairs***.
4. Pincha en ***Create Key Pair***  para crear un par de claves con el nombre **ssh01**. Observa que se descarga la clave privada (el cloud no almacena la clave privada, por eso se puede descargar).
![Claves SSH](img/claves.png)
5. Crea una nueva instancia con el nombre **cirros03** inyectando la clave pública del par de claves que has creado. Para ello en el momento de la creación (como has hecho en prácticas anteriores) en la sección ***Key Pairs***  selecciona la clave **ssh01**. 
![Inyectar la clave SSH](img/inyectar.png)
6. Asígnale una IP flotante a la instancia y verifica que existe la regla para permitir el acceso SSH en el grupo de seguridad *default*.
![Inyectar la clave SSH](img/instancia.png)
7. Copia la clave privada descargada en el directorio **.ssh** del directorio home de tu usuario (~./ssh).
8. Dale permisos restrictivos (600) a la clave privada.

	 ```chmod 600 ~/ssh01.pem```

9. Establece la conexión SSH y observa que no se pide la contraseña.

	```ssh -i ~/ssh01.pem cirros@ipflotante```

![Conexión autenticandose con clave pública](img/conexión.png)

En el siguiente [enlace](https://creodias.eu/faq-openstack/-/asset_publisher/TpmSvaqp3CVd/content/how-to-access-vm-from-windows-putty-?inheritRedirect=true) purdes ver como conectarte usando Putty como cliente. 