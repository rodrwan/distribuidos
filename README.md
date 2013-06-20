Distribuidos
============

Explicación para uso de *rest_in_python.py*

Para obtener la lista de usuarios se utiliza la siguiente url:

> http://localhost:8080/users GET

Lo cual nos entrega todos los usuarios que están registrados.

En el caso de que se quiera obtener los datos de un usuario en especifico se utiliza la siguiente url:

> http://localhost:8080/users/id_usuario GET

donde el id_usuario es el id del usuario que se quiere obtener la información.

Luego para agragar un nuevo usuario al sistema se realiza con la siguiente url:

> http://localhost:8080/users/new POST

y como paramétros recibe:

- first_name
- last_name


