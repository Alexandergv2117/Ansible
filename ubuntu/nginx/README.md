# NGINX

## Instalar NGINX

Para instalar nginx en un servidor remoto se debe ejecutar el siguiente comando,
previamente, se debe configurar el archivo `hosts` en el directorio `/etc/ansible`.

Te pedirá la contraseña de sudo antes de correr el playbook.

```bash
ansible-playbook install.yml --ask-become-pass
```

## Desinstalar NGINX

Para desinstalar nginx en un servidor remoto se debe ejecutar el siguiente comando.

Te pedirá la contraseña de sudo antes de correr el playbook.

```bash
ansible-playbook uninstall.yml --ask-become-pass
```

## Crear un virtual host y subir la configuración

Para crear un virtual host y subir la configuración a un servidor remoto se debe ejecutar el siguiente comando.

Te pedirá la contraseña de sudo antes de correr el playbook.

A manera de demostración se ha creado un archivo de configuración de virtual host en el directorio `example`. Si deseas puedes crear tu propio archivo de configuración y 
especificar la ruta en el comando. Así como el nombre del sitio y del servidor.

```bash
ansible-playbook create-virtual-host.yml -e "site_name=mi_sitio server_name=mi_sitio.com config_src=./example/virtualhost.conf" --ask-become-pass
```

### Parámetros

- `site_name` es el nombre del sitio.
- `server_name` es el nombre del servidor.
- `config_src` es la ruta del archivo de configuración del virtual host.

## Subir una página web

Para subir una página web a un servidor remoto se debe ejecutar el siguiente comando.

Te pedirá la contraseña de sudo antes de correr el playbook.

A manera de demostración se ha creado una carpeta `mi_sitio` con una página web en el directorio `example`. Si deseas puedes crear tu propia página web y
especificar la ruta en el comando. Así como el nombre del sitio.

```bash
ansible-playbook upload-website.yml -e "site_name=mi_sitio site_src=./example/mi_sitio" --ask-become-pass
```

### Parámetros

- `site_name` es el nombre del sitio.
- `site_src` es la ruta de la página web.

## Eliminar una página web

Para eliminar una página web de un servidor remoto se debe ejecutar el siguiente comando.

Te pedirá la contraseña de sudo antes de correr el playbook.

```bash
ansible-playbook delete-website.yml -e "site_name=mi_sitio2" --ask-become-pass
```

### Parámetros

- `site_name` es el nombre del sitio.

## Verificar la página web con curl

Para verificar que la página web se ha subido correctamente se puede ejecutar el siguiente comando.

#### Sin DNS

```bash
  curl --resolve [SERVER_NAME]:[PORT]:[IP] [SERVER_NAME]
```

### Parámetros

- `SERVER_NAME` es el nombre del servidor.
- `PORT` es el puerto.
- `IP` es la dirección IP del servidor remoto.

#### Con DNS

```bash
  curl [DNS]
```

### Parámetros

- `DNS` es el nombre del servidor.

## Eliminar un virtual host

Para eliminar un virtual host de un servidor remoto se debe ejecutar el siguiente comando.

Te pedirá la contraseña de sudo antes de correr el playbook.

```bash
ansible-playbook remove-virtual-host.yml -e "site_name=mi_sitio" --ask-become-pass
```

### Parámetros

- `site_name` es el nombre del sitio.

## Desabilitar un virtual host

Para desabilitar un virtual host de un servidor remoto se debe ejecutar el siguiente comando.

Te pedirá la contraseña de sudo antes de correr el playbook.

```bash
ansible-playbook disable-virtual-host.yml -e "site_name=mi_sitio" --ask-become-pass
```

### Parámetros

- `site_name` es el nombre del sitio.

## Habilitar un virtual host

Para habilitar un virtual host de un servidor remoto se debe ejecutar el siguiente comando.

Te pedirá la contraseña de sudo antes de correr el playbook.

```bash
ansible-playbook enable-virtual-host.yml -e "site_name=mi_sitio" --ask-become-pass
```

### Parámetros

- `site_name` es el nombre del sitio.