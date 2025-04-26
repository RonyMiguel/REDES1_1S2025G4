# Proyecto 2
## Área CUNDECH
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/5ac2dbfa2af5797d1dc87c572ce840db72642e3f/Proyecto%202/imagenes/CUNDECH.png)

### Tabla VLSM  

| Nombre VLAN  | VLAN | Host | n | Número máximo de Host (2^n) | Subred         | Primer Host     | Último Host     | Broadcast       | Máscara de red         |
|--------------|------|------|---|-----------------------------|----------------|------------------|------------------|------------------|-------------------------|
| Biblioteca   | 44   | 100  | 7 | 128                         | 192.168.4.0     | 192.168.4.1      | 192.168.4.126    | 192.168.4.127    | /25 (255.255.255.128)   |
| Estudiantes  | 14   | 50   | 6 | 64                          | 192.168.4.128   | 192.168.4.129    | 192.168.4.190    | 192.168.4.191    | /26 (255.255.255.192)   |
| Docentes     | 24   | 20   | 5 | 32                          | 192.168.4.192   | 192.168.4.193    | 192.168.4.222    | 192.168.4.223    | /27 (255.255.255.224)   |

### Tabla de PCs

| PCS           | IP              | Subnet mask        | Default Gateway    |
|---------------|------------------|--------------------|--------------------|
| Seguridad2    | 192.168.4.226     | 255.255.255.248     | 192.168.4.225      |
| Biblioteca3   | 192.168.4.2       | 255.255.255.128     | 192.168.4.1        |
| Biblioteca4   | 192.168.4.3       | 255.255.255.128     | 192.168.4.1        |
| Estudiantes6  | 192.168.4.130     | 255.255.255.192     | 192.168.4.129      |
| Estudiantes7  | 192.168.4.131     | 255.255.255.192     | 192.168.4.129      |
| Docentes6     | 192.168.4.195     | 255.255.255.224     | 192.168.4.193      |
| Docentes7     | 192.168.4.194     | 255.255.255.224     | 192.168.4.193      |

##  Área CUNOROC
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/5ac2dbfa2af5797d1dc87c572ce840db72642e3f/Proyecto%202/imagenes/CUNOROC.png)

### Tabla VLANs 
| Nombre VLAN | VLAN | n | Número máximo de Host (2^n) | Subred          | Primer Host     | Último Host     | Broadcast       | Máscara de red             |
|-------------|------|---|-----------------------------|-----------------|-----------------|-----------------|-----------------|-----------------------------|
| Biblioteca  | 44   | 7 | 128                         | 192.148.4.0     | 192.148.4.1     | 192.148.4.126   | 192.148.4.127   | /25 (255.255.255.128)       |
| Estudiantes | 14   | 6 | 64                          | 192.148.4.128   | 192.148.4.129   | 192.148.4.190   | 192.148.4.191   | /26 (255.255.255.192)       |
| Docentes    | 24   | 5 | 32                          | 192.148.4.192   | 192.148.4.193   | 192.148.4.222   | 192.148.4.223   | /27 (255.255.255.224)       |
| Seguridad   | 34   | 4 | 16                          | 192.148.4.224   | 192.148.4.225   | 192.148.4.238   | 192.148.4.239   | /28 (255.255.255.240)       |

### Tabla de PCs 

| PCS          | IP              | Subnet mask        | Default Gateway    |
|--------------|------------------|--------------------|--------------------|
| Seguridad3   | 192.148.4.226     | 255.255.255.240     | 192.148.4.225      |
| Biblioteca1  | 192.148.4.2       | 255.255.255.128     | 192.148.4.1        |
| Estudiantes3 | 192.148.4.130     | 255.255.255.192     | 192.148.4.129      |
| Docentes3    | 192.148.4.194     | 255.255.255.224     | 192.148.4.193      |

##Área Central

### Tabla VLANs 
### Tabla de Servidores - Central

| Servidor | VLAN | Red             | Gateway        | IP del servidor  | Máscara de red    |
|----------|------|-----------------|----------------|------------------|-------------------|
| Server0  | 50   | 192.120.4.0   | 192.120.4.1    | 192.120.4.10     | /24 (255.255.255.0)    |
| Server1  | 61   | 192.121.4.0   | 192.121.4.1    | 192.121.4.10     | /24 (255.255.255.0)    |
| Server2  | 72   | 192.122.4.0   | 192.122.4.2    | 192.122.4.10     | /24 (255.255.255.0)    |

## Área CUNOC
### Tabla VLSM 
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/5ac2dbfa2af5797d1dc87c572ce840db72642e3f/Proyecto%202/imagenes/CUNOC.png
)
**ID de Red:** 172.16.4.0/24

| Nombre VLAN | VLAN | Hosts | Subred | IP de red      | Máscara           | Primer Host     | Último Host     | Broadcast       |
|-------------|------|-------|--------|----------------|-------------------|-----------------|-----------------|-----------------|
| Estudiantes | 14   | 60    | 1      | 172.16.4.0     | 255.255.255.192   | 172.16.4.1      | 172.16.4.62     | 172.16.4.63     |
| Docentes    | 24   | 35    | 3      | 172.16.4.128   | 255.255.255.192   | 172.16.4.129    | 172.16.4.190    | 172.16.4.191    |
| Seguridad   | 34   | 5     | 4      | 172.16.4.192   | 255.255.255.248   | 172.16.4.193    | 172.16.4.198    | 172.16.4.199    |
| Biblioteca  | 44   | 50    | 2      | 172.16.4.64    | 255.255.255.192   | 172.16.4.65     | 172.16.4.126    | 172.16.4.127    |

### Tabla de PCs 

| PCS           | IP               | Default Gateway   | Máscara              |
|---------------|------------------|-------------------|----------------------|
| Docentes 1    | 172.16.4.130     | 172.16.4.129      | 255.255.255.192      |
| Docentes 2    | 172.16.4.131     | 172.16.4.129      | 255.255.255.192      |
| Seguridad 4   | 172.16.4.196     | 172.16.4.193      | 255.255.255.248      |
| Estudiantes 1 | 172.16.4.4       | 172.16.4.1        | 255.255.255.192      |
| Estudiantes 2 | 172.16.4.3       | 172.16.4.1        | 255.255.255.192      |

## CUM
![](https://github.com/RonyMiguel/REDES1_1S2025G4/blob/5ac2dbfa2af5797d1dc87c572ce840db72642e3f/Proyecto%202/imagenes/CUM.png
)

### Tabla VLSM
**ID de red:** `192.158.4.0/24`

| Nombre       | VLAN | Hosts | Subred | IP de red       | Máscara           | Primer Host     | Último Host     | Broadcast       |
|--------------|------|--------|--------|------------------|-------------------|------------------|------------------|------------------|
| Estudiantes  | 14   | 45     | 2      | 192.158.4.128   | 255.255.255.192   | 192.158.4.129    | 192.158.4.190    | 192.158.4.191    |
| Docentes     | 24   | 25     | 3      | 192.158.4.192   | 255.255.255.224   | 192.158.4.193    | 192.158.4.222    | 192.158.4.223    |
| Seguridad    | 34   | 10     | 4      | 192.158.4.224   | 255.255.255.240   | 192.158.4.225    | 192.158.4.238    | 192.158.4.239    |
| Biblioteca   | 44   | 75     | 1      | 192.158.4.0     | 255.255.255.128   | 192.158.4.1      | 192.158.4.126    | 192.158.4.127    |

#### Tabla de PCs

| Dispositivo      | IP              | Gateway         | Máscara           |
|------------------|------------------|------------------|--------------------|
| Estudiantes 5    | 192.158.4.132    | 192.158.4.129    | 255.255.255.192    |
| Docentes 5       | 192.158.4.196    | 192.158.4.193    | 255.255.255.224    |
| Seguridad 1      | 192.158.4.228    | 192.158.4.225    | 255.255.255.240    |
| Biblioteca 2     | 192.158.4.4      | 192.158.4.1      | 255.255.255.128    |


## Comandos

Switch Modo Server
```bash
enable
configure terminal
vtp domain Grupo4
vtp password usac2025
vtp mode server
vtp version 2

//Creacion de VLANs
vlan 14
name Estudiantes
vlan 24
name Docentes
vlan 34
name Seguridad
vlan 44
name Biblioteca
exit

//Interface de salida
interface fa0/#
switchport mode trunk
switchport encapsulation dot1q
switchport trunk allowed vlan 14,24,34,44
exit
```

Switches Modo Cliente
```bash
enable
configure terminal
vtp domain Grupo4
vtp password usac2025
vtp mode client
vtp version 2

//Permitir vlan en interface
interface fa0/#interface
switchport mode access
switchport access vlan #vlan
exit
```

HSRP en Switch
```bash
// Asignar una ip por red/vlan a cada switch
enable
configure terminal
ip routing

// Se crean las mismas vlans
vlan 14
name Estudiantes
vlan 24
name Docentes
vlan 34
name Seguridad
vlan 44
name Biblioteca
exit

//se asigna informacion por cada vlan
interface vlan#
ip address <IP> <Mascara de Red>

//Configuracion hsrp con stanby version 2
//Se usa la ip que es gateway como una ip virtual
//Se le asigna un numero unico a cada standby, ej 1
standby 1 ip xxx.xxx.xxx.xxx
//Por defecto tiene 100 de prioridad, si queremos que tenga mayor prioridad esta se asigna
standby 1 priority 150
standby 1 preempt
standby version 2
exit

//Finalmente se deja la interface a utilizar en modo trunk
interface fa0/#
switchport mode trunk
```

HSRP en Router
```bash
enable
configure terminal

//Se utiliza router on stick para cada vlan xx
interface gi0/1.xx
encapsulation dot1q xx
ip address <IP> <Mascara de Red>
//Configuracion hsrp con stanby version 2
//Se usa la ip que es gateway como una ip virtual
//Se le asigna un numero unico a cada standby, ej 1
standby 1 ip xxx.xxx.xxx.xxx
//Por defecto tiene 100 de prioridad, si queremos que tenga mayor prioridad esta se asigna
standby 1 priority 150
standby 1 preempt
standby version 2
exit
```
