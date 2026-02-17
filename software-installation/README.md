# software-installation (AAP)

Proyecto Ansible para **instalación de software** en:

- **Linux** (grupo: `LINUX`)
- **Windows PROD** (grupo: `PROD`)
- **Windows DRP** (grupo: `DRP`)

Genera reportes **CSV** y **HTML** en el nodo de control `invd-ts-ansible` al finalizar la ejecución.

## Estructura
- `run_software_installation.yml` : playbook principal
- `roles/software_installation/vars/packages_linux.yml` : catálogo de paquetes Linux (extensible)
- `roles/software_installation/vars/packages_windows.yml` : catálogo de paquetes Windows (extensible)
- `roles/software_installation/templates/` : plantillas CSV/HTML
- `roles/software_installation/tasks/` : lógica de instalación y generación de reportes

## Ejecución
Desde AAP, crea un **Project** apuntando a este repositorio y un **Job Template** que ejecute:

- Playbook: `run_software_installation.yml`

## Reportes
Por default se generan en:

`/reportes_ansible/software_installation/<TIMESTAMP>/`

Archivos:
- `linux_software_installation.csv` / `.html`
- `windows_software_installation.csv` / `.html`

## Notas importantes
- Linux: se asume que el repositorio de paquetes está disponible en el controller en: `/software_repo`
- Windows: se asume que los servidores tienen acceso al share UNC configurado en `packages_windows.yml`
