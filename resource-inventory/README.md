# resource-inventory (AAP Project) - Asset Inventory

Actualizacion: deteccion mas fina para:
- Windows: NIC basada en default route, VLAN real (NetAdapterVlan/AdvancedProperty), hipervisor (VMware/Hyper-V/KVM/Xen/VirtualBox/AWS).
- Linux: hipervisor con systemd-detect-virt (si existe), VLAN (subinterfaz/ip -d link/bridge vlan), speed (ethtool/sysfs).

Los reportes CSV/HTML mantienen las mismas columnas.
