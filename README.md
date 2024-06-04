# Ansible

## Configuración de hosts

Para poder ejecutar los playbooks de ansible es necesario configurar los hosts en el archivo `hosts` que se encuentra en el directorio
```bash
/etc/ansible
```
Si no existe el archivo `hosts` se puede crear con el siguiente comando
```bash
sudo touch /etc/ansible/hosts
```

Ejemplo de configuración de hosts
```bash
[GRUPO]
[HOST] ansible_port=[PORT] ansible_user=[USER] ansible_ssh_private_key_file=[PRIVATE KEY]
```

`GRUPO` es el nombre del grupo al que pertenece el host.
`HOST` es la dirección IP o el DNS del host al que se va a conectar.
`PORT` es el puerto por el cual se va a conectar al host.
`USER` es el usuario con el que se va a conectar al host.
`PRIVATE KEY` es la ruta del archivo de la llave privada con la que se va a conectar al host.

> [!NOTE]
> - Puede haber varios grupos en el archivo `hosts`.
> - Se pueden tener varios servidores en un mismo grupo.

## NOTES

> [!IMPORTANT]
> Con este parametro Ansible te pedira la contraseña de sudo antesn de correr el playbook.
> 
>  ```bash
> --ask-become-pass
>  ```
> 
> Ejemplo
>  ```bash
> ansible-playbook install.yml --ask-become-pass
>  ```
