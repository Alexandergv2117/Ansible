# Docker

## Instalar Docker

Para instalar Docker en un servidor remoto se debe ejecutar el siguiente comando.

Te pedirá la contraseña de sudo antes de correr el playbook.
  
```bash
ansible-playbook install-docker.yml --ask-become-pass
```

## Eliminar Docker

Para eliminar Docker de un servidor remoto se debe ejecutar el siguiente comando.

Te pedirá la contraseña de sudo antes de correr el playbook.

```bash
ansible-playbook remove-docker.yml --ask-become-pass
```