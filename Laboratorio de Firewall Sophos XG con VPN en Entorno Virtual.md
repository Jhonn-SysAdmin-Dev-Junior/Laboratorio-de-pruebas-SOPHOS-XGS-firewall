## 🛠️ Herramientas utilizadas

- **VirtualBox**
- **Sophos XG Home Edition** – Firewall virtualizado.
  
---

## 🧩 Objetivos del laboratorio

- Simular un entorno real de red segura.
- Configurar reglas de firewall y control de acceso.
- Habilitar y probar una **VPN SSL** remota.
- Administrar usuarios, grupos y políticas.

---

## 🧪 Proceso de configuración y pruebas

### 🔹 1. Configuración inicial de Sophos
- Instalación de Sophos XG en VM.
<img src="imgs/instalacion1.png" width="500">
- Asignación de interfaces LAN y WAN.
<img src="imgs/LAN.png" width="500">
<img src="imgs/WAN.png" width="500">

### 2. 🧱 VLANs y Segmentación
- Creación de VLANs en la red LAN para segmentar el tráfico interno.
<img src="imgs/Vlan.png" width="500">
- Para crear correctamente una VLAN en Sophos, primero se debe crear una zona, ya que la interfaz VLAN debe estar asignada a una zona para su gestión y control de tráfico.
<img src="imgs/zona.png" width="500">
- Asignacion de DHCP para la Vlan.
<img src="imgs/dhcp.png" width="500">
  
### 🔹 3. Políticas y reglas de firewall
- Creación de políticas de firewall entre zonas
<img src="imgs/reglas.png" width="500">


### 🔹 4. Configuración de VPN SSL
- Se creó un usuario local y un grupo de usuarios VPN.  
  ![vpn](imgs/vpn.png)

- Se asignó al usuario una política de VPN SSL específica.  
  ![política](imgs/politica.png)

- Se habilitó el acceso a la LAN y a Internet desde la VPN.  
  ![política](imgs/politica.png)

- Se generó el archivo de configuración `.ovpn` para importar al cliente Sophos Connect.  
  ![política](imgs/politica.png)

- Se descargó e instaló el cliente VPN en el equipo host.  
  ![política](imgs/politica.png)

- Se importó el archivo `.ovpn` al cliente para establecer la conexión.  
  ![política](imgs/politica.png)

- La VPN se probó correctamente y se pudo acceder a la red interna y navegar por internet.  
  ![política](imgs/politica.png)

- Se creó una regla de firewall para permitir tráfico desde la VPN a la LAN y WAN.  
  ![política](imgs/politica.png)

- Se ajustó el acceso desde zonas para permitir portal VPN y SSL VPN desde WAN.  
  ![política](imgs/politica.png)

- Se validó el tráfico VPN con la ruta `ip route` en el cliente.

- Simulación de un entorno real de red segura.

