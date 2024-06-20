# Usuarios LINUX

## Añadir un usuario a uno o mas grupos

Para añadir un usuario a uno o mas grupos se debe ejecutar el siguiente comando.

Te pedirá la contraseña de sudo antes de correr el playbook.

```bash
ansible-playbook add-user-to-groups.yml -e "user_name=ubuntu group_names=docker" --ask-become-pass
```

### Parámetros

- `user_name`: Nombre del usuario al que se le añadirá uno o mas grupos.
- `group_names`: Nombre de uno o mas grupos separados por comas.

> [!IMPORTANT]
> El usuario debe reiniciar la sesión para que los cambios surtan efecto.

## Eliminar un usuario de uno o mas grupos

Para eliminar un usuario de uno o mas grupos se debe ejecutar el siguiente comando.

Te pedirá la contraseña de sudo antes de correr el playbook.

```bash
ansible-playbook remove-user-from-groups.yml -e "user_name=ubuntu group_names=docker" --ask-become-pass
```

### Parámetros

- `user_name`: Nombre del usuario al que se le eliminará de uno o mas grupos.
- `group_names`: Nombre de uno o mas grupos separados por comas.

> [!IMPORTANT]
> El usuario debe reiniciar la sesión para que los cambios surtan efecto.
