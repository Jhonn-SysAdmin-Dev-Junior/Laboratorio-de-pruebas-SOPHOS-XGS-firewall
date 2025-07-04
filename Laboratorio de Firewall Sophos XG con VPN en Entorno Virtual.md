## 🛠️ Herramientas utilizadas

- **VirtualBox** / **VMware** – Hypervisor para las MVs.
- **Sophos XG Home Edition** – Firewall perimetral virtualizado.
- **Cliente VPN SSL de Sophos** – Para conexión remota al firewall.
- **Host local Windows/Linux** – Como cliente de prueba.
- Red interna y simulación WAN para probar accesos externos.

---

## 🧩 Objetivos del laboratorio

- Simular un entorno real de red segura.
- Configurar reglas de firewall y control de acceso.
- Habilitar y probar una **VPN SSL** remota.
- Administrar usuarios, grupos y políticas.
- Documentar errores y soluciones encontradas.

---

## 🧪 Proceso de configuración y pruebas

### 🔹 1. Configuración inicial de Sophos
- Instalación de Sophos XG en VM.
<img src="imgs/instalacion1.png" width="600">
- Asignación de interfaces LAN y WAN.
<img src="imgs/LAN.png" width="600">
<img src="imgs/WAN.png" width="600">

### 2. 🧱 VLANs y Segmentación
- Creación de VLANs en la red LAN para segmentar el tráfico interno.

- Configuración de rutas y acceso entre segmentos internos mediante reglas explícitas.

### 🔹 3. Políticas y reglas de firewall
- Se eliminaron políticas SSL y reglas innecesarias para limpiar la configuración.
- No se podía asignar usuarios a ciertos grupos hasta vaciar dependencias.

### 🔹 4. Configuración de VPN SSL
- Se habilitó el acceso VPN por WAN.
- El cliente SSL VPN fue descargado e instalado correctamente.
- Al intentar conectarse, la VPN se conectaba pero **desconectaba de inmediato.**

### 🔹 5. Solución al problema de desconexión
- Se revisaron **reglas ACL y acceso remoto al portal de usuarios.**
- Se verificó que la interfaz WAN permite acceso SSL VPN (puerto 8443).
- Se examinó el archivo `.ovpn` y se confirmó que contiene múltiples rutas de fallback (`remote`).
- Se dejó clara la diferencia entre editar el `.ovpn` directamente vs. regenerarlo tras cambios en el firewall.

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
