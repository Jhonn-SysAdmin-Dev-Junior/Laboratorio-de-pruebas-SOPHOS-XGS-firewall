🛠️ Herramientas utilizadas

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
<ul>
  <li>
    <p>Instalación de Sophos XG en VM.</p>
    <img src="imgs/instalacion1.png" width="500">
  </li>

  <li>
    <p>Asignación de interfaces LAN y WAN.</p>
    <img src="imgs/LAN.png" width="500">
    <img src="imgs/WAN.png" width="500">
  </li>
</ul>

### 2. 🧱 VLANs y Segmentación
<ul>
  <li>
    <p>Para crear correctamente una VLAN en Sophos, primero se debe crear una zona, ya que la interfaz VLAN debe estar asignada a una zona para su gestión y control de tráfico.</p>
    <img src="imgs/zona.png" width="500">
  </li>
  <li>
     <p>Creación de VLANs en la red LAN para segmentar el tráfico interno.</p>
      <img src="imgs/Vlan.png" width="500">
  </li>
  <li>
    <p>Asignacion de DHCP para la Vlan.</p>
    <img src="imgs/dhcp.png" width="500">
  </li>
</ul>
  
### 🔹 3. Políticas y reglas de firewall
<ul>
  <li>
    <p>Es necesario la creación de una regla de firewall para permitir que los usuarios que estan en la VLAN puedan acceder a la WAN (Internet)</p>
  <img src="imgs/reglas.png" width="400">
  </li>
  <li>
 <p>Para verificar que la VLAN fue creada correctamente y funciona según lo esperado, se utilizará una máquina virtual con Linux. Esto se debe a que sistemas como Windows no soportan el etiquetado VLAN. Es importante que esta máquina virtual esté conectada a la misma red interna que el firewall (por ejemplo, mediante un adaptador de red en modo "Red Interna") para poder ejecutar los comandos necesarios y comprobar la conectividad dentro del entorno VLAN.</p>
<p>Para esto ejecutamos los comandos:</p>
<p>
sudo ip link add link enp0s8 name enp0s8.10 type vlan id 10 (crear la interfaz VLAN 10 sobre enp0s8)</p>
<b>sudo ip link set dev enp0s8.10 up (levantar la interfaz VLAN)</b>
    
  </li>
</ul>



### 🔹 4. Configuración de VPN SSL
<ul>
  <li>
    <p>Se creó un usuario local y un grupo de usuarios VPN.</p>
    <img src="imgs/vpn.png" width="500">
  </li>
  <li>
    <p>Se asignó al usuario una política de VPN SSL específica.</p>
    <img src="imgs/politica.png" width="500">
  </li>
  <li>
    <p>Se habilitó el acceso a la LAN y a Internet desde la VPN.</p>
    <img src="imgs/politica.png" width="500">
  </li>
  <li>
    <p>Se generó el archivo de configuración .ovpn para importar al cliente Sophos Connect.</p>
    <img src="imgs/politica.png" width="500">
  </li>
  <li>
    <p>Se descargó e instaló el cliente VPN en el equipo host.</p>
    <img src="imgs/politica.png" width="500">
  </li>
  <li>
    <p>Se importó el archivo .ovpn al cliente para establecer la conexión.</p>
    <img src="imgs/politica.png" width="500">
  </li>
  <li>
    <p>La VPN se probó correctamente y se pudo acceder a la red interna y navegar por internet.</p>
    <img src="imgs/politica.png" width="500">
  </li>
  <li>
    <p>Se creó una regla de firewall para permitir tráfico desde la VPN a la LAN y WAN.</p>
    <img src="imgs/politica.png" width="500">
  </li>
  <li>
    <p>Se ajustó el acceso desde zonas para permitir portal VPN y SSL VPN desde WAN.</p>
    <img src="imgs/politica.png" width="500">
  </li>
  <li>
    <p>Se validó el tráfico VPN con la ruta <code>ip route</code> en el cliente.</p>
  </li>
</ul>



