# REDES1_1S2025G4
## Tablas De IP  Vlan
| Área de desarrollo      | Vlan         | ID de red    |
|:------------------------|:------------|:-------------|
| Ventas                 | 14          | 192.168.14.2 |
|                        |             | 192.168.14.3 |
| Soporte                | 24          | 192.168.24.2 |
|                        |             | 192.168.24.3 |
| Gerencia               | 34          | 192.168.34.5 |
| Seguridad              | 44          | 192.164.44.7 |
|                        |             | 192.164.44.2 |

### Área de Gerencia  
| Departamento | Vlan | ID de red     |
|-------------|------|--------------|
| Soporte     | 24   | 192.168.24.5  |
| Gerencia    | 34   | 192.168.34.3  |
|             |      | 192.168.34.4  |
| Seguridad   | 44   | 192.164.44.3  |

### Área de Infraestructura  
| Departamento | Vlan | ID de red     |
|-------------|------|--------------|
| Ventas      | 14   | 192.168.14.4  |
| Soporte     | 24   | 192.168.24.4  |
| Seguridad   | 44   | 192.164.44.5  |
|             |      | 192.164.44.6  |

### Área de Administración  
| Departamento | Vlan | ID de red     |
|-------------|------|--------------|
| Ventas      | 14   | 192.168.14.1  |
|             |      | 192.168.14.5  |
| Soporte     | 24   | 192.168.24.1  |
| Gerencia    | 34   | 192.168.34.1  |
|             |      | 192.168.34.2  |
| Seguridad   | 44   | 192.164.44.1  |
| Recepción   | 54   | 192.164.54.1  |
|             |      | 192.164.54.2  |
|             |      | 192.164.54.3  |
|             |      | 192.164.54.4  |

### Área Central  
| Vlan  |
|------|
| 14   |
| 24   |
| 34   |
| 44   |
| 54   |
![Ping AU1 - RyM1]()
##Topologías implementadas
### Área Administración
![Ping AU1 - RyM1](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/f941ae097c5944c0fc2d838366da187817a28e2f/Aa.png)
### Área central
![Ping AU1 - RyM1](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/f941ae097c5944c0fc2d838366da187817a28e2f/Ac.png)
### Área Desarrollo
![Ping AU1 - RyM1](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/f941ae097c5944c0fc2d838366da187817a28e2f/Ad.png)
### Área Gerencia
![Ping AU1 - RyM1](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/f941ae097c5944c0fc2d838366da187817a28e2f/Ag.png)
### Area infraestructura
![Ping AU1 - RyM1](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/f941ae097c5944c0fc2d838366da187817a28e2f/Ai.png)

## Ping entre Hosts
Ping gerencia 1 a gerencia 2
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/04349ac4145eeb2b5114ae529ad6c20904d4caf8/p12.jpg)

Ping Seguridad 1  a gerencia 2
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/04349ac4145eeb2b5114ae529ad6c20904d4caf8/P22.jpg)

Ping Soporte tecnico 5 a Soporte técnico 2
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/04349ac4145eeb2b5114ae529ad6c20904d4caf8/p23.jpg)
Ping Ventas 4 a Ventas 1
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/04349ac4145eeb2b5114ae529ad6c20904d4caf8/p4.jpg)
Ping Recepción 1 a recepción 4
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/04349ac4145eeb2b5114ae529ad6c20904d4caf8/p5.jpg)




# Comandos

## Server
```
enable
configure terminal
vtp domain G4_technet
vtp password secure2025
vtp mode server
vtp version 2

vlan 14
name Ventas
exit

vlan 24
name Soporte
exit

vlan 34
name Gerencia
exit

vlan 44
name Seguridad
exit

interface range fa0/1-n
switchport trunk encapsulation dot1q
switchport mode trunk
switchport trunk allowed vlan 14,24,34,44
```

## STP
```
spanning-tree vlan 14,24,34,44 root primary
do wr
```

## Switches Clientes
```
enable
configure terminal
vtp domain G4_techent
vtp password secure2025
vtp mode client

interface fa0/#puerto/s de escucha
switchport trunk encapsulation dot1q //Solo capa 3
switchport mode trunk
switchport trunk allowed vlan 14,24,34,44
do wr
exit

interface fa0/#puerto/s a hosts
switchport mode access
switchport access vlan #vlan_a_permitir
do wr
exit
```

## Modo Transparente
```
enable
configure terminal
vtp domain G4_techent
vtp password secure2025
vtp mode transparente

vlan 14
name Ventas
exit

vlan 24
name Soporte
exit

vlan 34
name Gerencia
exit

vlan 44
name Seguridad
exit

vlan 54
name Recepcion
exit

interface fa0/#puerto/s de escucha
switchport mode trunk
switchport trunk allowed vlan 14,24,34,44
do wr
exit

interface fa0/#puerto/s a hosts
switchport mode access
switchport access vlan #vlan_a_permitir
do wr
exit
```

