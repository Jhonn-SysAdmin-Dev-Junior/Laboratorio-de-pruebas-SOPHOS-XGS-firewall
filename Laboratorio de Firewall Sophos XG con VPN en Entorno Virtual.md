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
<img src="imgs/instalacion1.png" width="600">
<br>
- Asignación de interfaces LAN y WAN.
  <br>
<img src="imgs/LAN.png" width="600">
<img src="imgs/WAN.png" width="600">

### 2. 🧱 VLANs y Segmentación
- Creación de VLANs en la red LAN para segmentar el tráfico interno.
<img src="imgs/Vlan.png" width="600">
- Para crear correctamente una VLAN en Sophos, primero se debe crear una zona, ya que la interfaz VLAN debe estar asignada a una zona para su gestión y control de tráfico.
<br>
<img src="imgs/zona.png" width="600">
- Asignacion de DHCP para la Vlan.
<br>
<img src="imgs/dhcp.png" width="600">
  
### 🔹 3. Políticas y reglas de firewall
- Creación de políticas de firewall entre zonas
<img src="imgs/reglas.png" width="300">


### 🔹 4. Configuración de VPN SSL
- Se creó un usuario local y un grupo de usuarios VPN.
<img src="imgs/vpn.png" width="300">
- Se asignó al usuario una política de VPN SSL específica.
<img src="imgs/politica.png" width="300">



---

## 🧱 Estructura esperada del laboratorio

```bash
📁 laboratorio-sophos-vpn
├── vpn-config/
│   ├── cliente-vpn.ovpn
│   └── notas-configuracion.md
├── capturas/
│   ├── error-vpn.png
│   └── interfaz-firewall.png
├── README.md
