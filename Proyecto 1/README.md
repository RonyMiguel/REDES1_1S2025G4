# REDES1_1S2025G4
Carnet 201905750
Carnet 202001814
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
## Ping gerencia 1 a gerencia 2
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/04349ac4145eeb2b5114ae529ad6c20904d4caf8/p12.jpg)

### Ping Seguridad 1  a gerencia 2
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/04349ac4145eeb2b5114ae529ad6c20904d4caf8/P22.jpg)

### Ping Soporte tecnico 5 a Soporte técnico 2
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/04349ac4145eeb2b5114ae529ad6c20904d4caf8/p23.jpg)
### Ping Ventas 4 a Ventas 1
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/04349ac4145eeb2b5114ae529ad6c20904d4caf8/p4.jpg)
### Ping Recepción 1 a recepción 4
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



##  Presupuesto del Proyecto de Redes
###  Equipos de Red
| Cantidad | Dispositivo                | Modelo recomendado | Precio unitario (GTQ) | Subtotal (GTQ) |
|----------|----------------------------|--------------------|----------------------|---------------|
| 1        | **Switch Core** (Backbone)  | Cisco Catalyst 2960-X | 3,500  | 3,500  |
| 4        | **Switches de acceso** (Clientes) | Cisco Catalyst 2960 | 2,500  | 10,000 |
| 1        | **Switch Transparente**     | Cisco Catalyst 2960 | 2,500  | 2,500  |
| 2        | **Switches con EtherChannel** | Cisco Catalyst 3750 | 4,500  | 9,000  |
| 10       | **Computadoras de prueba**  | PC estándar (Intel i5, 8GB RAM) | 3,800  | 38,000 |
| 1        | **Router para Inter-VLAN Routing** | Cisco ISR 4321 | 4,000  | 4,000  |

**Subtotal Equipos de Red:** **GTQ 67,000**

---

### Cables y Conectividad
| Cantidad | Descripción | Precio unitario (GTQ) | Subtotal (GTQ) |
|----------|------------|----------------------|---------------|
| 30       | Cable UTP Cat6 (1m) | 25 | 750  |
| 10       | Patch Cord Cat6 (3m) | 50 | 500  |
| 2        | Rack de servidores | 2,000 | 4,000 |
| 20       | Conectores RJ-45 | 2 | 40 |

**Subtotal Cables y Conectividad:** **GTQ 5,290**

---

### Licencias y Software
| Cantidad | Software/Servicio | Precio unitario (GTQ) | Subtotal (GTQ) |
|----------|------------------|----------------------|---------------|
| 1        | **Cisco Packet Tracer** | Gratis | 0 |
| 1        | **Windows 10 para PCs** | 600  | 600 |
| 1        | **Licencia de Switch Cisco** | 1,200  | 1,200 |
| 1        | **Licencia de Router Cisco** | 1,500  | 1,500 |

**Subtotal Licencias y Software:** **GTQ 3,300**

---

###  Mano de Obra e Instalación
| Descripción | Precio (GTQ) |
|-------------|------------|
| Configuración y pruebas de red | 1,500 |
| Instalación física del cableado | 1,000 |
| Soporte técnico inicial | 800 |

**Subtotal Mano de Obra:** **GTQ 3,300**

---

### **Total General del Proyecto:**
**Equipos de Red:** **GTQ 67,000**  
**Cables y Conectividad:** **GTQ 5,290**  
 **Licencias y Software:** **GTQ 3,300**  
 **Mano de Obra:** **GTQ 3,300**  
 **Total estimado: GTQ 78,890**

---

