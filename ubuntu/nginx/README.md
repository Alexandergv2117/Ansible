# NGINX

## Install NGINX

Para instalar nginx en un servidor remoto se debe ejecutar el siguiente comando,
previamente se debe configurar el archivo `hosts` en el directorio `/etc/ansible`.

Te pedira la contraseña de sudo antes de correr el playbook.

```bash
ansible-playbook install.yml --ask-become-pass
```

## Desinstalar NGINX

Para desinstalar nginx en un servidor remoto se debe ejecutar el siguiente comando.

Te pedira la contraseña de sudo antes de correr el playbook.

```bash
ansible-playbook uninstall.yml --ask-become-pass
```

## Crear un virtual host y subir la configuración

Para crear un virtual host y subir la configuración a un servidor remoto se debe ejecutar el siguiente comando.

Te pedira la contraseña de sudo antes de correr el playbook.

A manera de demostración se ha creado un archivo de configuración de virtual host en el directorio `example`. Si deaseas puedes crear tu propio archivo de configuración y 
especificar la ruta en el comando. Asi como el nombre del sitio y del servidor.

```bash
ansible-playbook create-virtual-host.yml -e "site_name=mi_sitio server_name=mi_sitio.com config_src=./example/virtualhost.conf"
```

### Parámetros

- `site_name` es el nombre del sitio.
- `server_name` es el nombre del servidor.
- `config_src` es la ruta del archivo de configuración del virtual host.

## Subir una página web

Para subir una página web a un servidor remoto se debe ejecutar el siguiente comando.

Te pedira la contraseña de sudo antes de correr el playbook.

A manera de demostración se ha creado una carpeta `mi_sitio` con una página web en el directorio `example`. Si deaseas puedes crear tu propia página web y
especificar la ruta en el comando. Asi como el nombre del sitio.

```bash
ansible-playbook upload-website.yml -e "site_name=mi_sitio site_src=./example/mi_sitio" --ask-become-pass
```

### Parámetros

- `site_name` es el nombre del sitio.
- `site_src` es la ruta de la página web.
