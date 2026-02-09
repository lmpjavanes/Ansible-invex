# resource-inventory (AAP Project)

Proyecto Ansible para recolectar información de recursos en servidores **Linux** y **Windows** usando catálogos de comandos, y generar reportes **CSV** y **HTML**.

## Estructura
- `run_resource_inventory.yml`: playbook principal (Linux + Windows + Control)
- `roles/resource_inventory/vars/`: catálogos de comandos por OS (YAML)
- `roles/resource_inventory/templates/`: templates de reportes CSV/HTML
- `roles/resource_inventory/tasks/`: ejecución y render

## Cómo agregar comandos
- Linux: editar `roles/resource_inventory/vars/commands_linux.yml`
- Windows: editar `roles/resource_inventory/vars/commands_windows.yml`

## Inventario (AAP)
Este playbook asume grupos:
- `LINUX`
- `WINDOWS`
y un host de control:
- `inv-ts-ansible`

## Salida
Los reportes se generan en:
`/reportes_ansible/resource_inventory/{{ ansible_date_time.iso8601_basic_short }}`
