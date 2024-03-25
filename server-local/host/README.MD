# ARCHIVO HOSTS
El archivo hosts en Ansible es un inventario, donde se ponen las lista de servidores a conectarse, el user y especificas las llaves SSH con las que te vas a conectar.

## EJEMPLO
En el archivo host.example que esta en la raíz de este directorio, se encuentra la configuración para conectarse a los diferentes servidores.
Este archivo se crea en `/etc/ansible/hosts` o en la raíz del proyecto.

### VARIABLES

`HOST`: Dirección IP o DNS del servidor.

`USER`: Usuario con el que se va a conectar, debe de ser el usuario del servidor remoto.

`PORT`: Puerto por el cual se va a conectar, por defecto es el 22. Este campo es opcional.

`PRIVATE KEY`: Ruta de la llave privada con la que se va a conectar. Este campo es opcional.

`GRUPO`: Grupo al que pertenece el servidor, se puede tener varios servidores en un mismo grupo.

## USO
```
ansible GRUPO -m ping
```