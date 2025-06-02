# Networking Linux Tools

Repositorio con comandos útiles para análisis, configuración y reparación de redes en Linux.

---

## Índice

1. [🧰 Herramientas de configuración y comprobación](./docs/herramientas.md)  
2. [📡 Escaneo y análisis de red](./docs/escaneo.md)  
3. [📄 Logs importantes para analizar errores](./docs/logs.md)  
4. [🛠️ Solución de problemas y reparación](./docs/reparacion.md)  
5. [🎯 Trucos útiles y recordatorios](./docs/trucos.md)  
6. [🔍 Comandos básicos de diagnóstico](./docs/basicos.md)

---

## 🔍 Comandos básicos de diagnóstico

- [`dig <dominio>`](./docs/basicos.md#dig) — Consulta DNS detallada.  
- [`host <dominio>`](./docs/basicos.md#host) — Resolución DNS básica.  
- [`ip a` o `ip addr`](./docs/basicos.md#ip-a) — Muestra interfaces y direcciones IP.  
- [`ip link`](./docs/basicos.md#ip-link) — Estado de interfaces de red.  
- [`ip r` o `ip route`](./docs/basicos.md#ip-r) — Tabla de rutas.  
- [`mtr <IP>`](./docs/basicos.md#mtr) — Diagnóstico continuo de red (mejor que traceroute).  
- [`nslookup <dominio>`](./docs/basicos.md#nslookup) — Consulta DNS básica.  
- [`ping <IP o dominio>`](./docs/basicos.md#ping) — Verifica conectividad.  
- [`traceroute <IP o dominio>`](./docs/basicos.md#traceroute) — Muestra la ruta que siguen los paquetes.  
- [`whois <dominio/IP>`](./docs/basicos.md#whois) — Información del dominio o IP.

---

## 🧰 Herramientas de configuración y comprobación

- [`cat /etc/resolv.conf`](./docs/herramientas.md#cat-etc-resolv-conf) — Verifica servidores DNS usados.  
- [`ifconfig`](./docs/herramientas.md#ifconfig) — Obsoleto pero útil en sistemas antiguos.  
- [`iwconfig`](./docs/herramientas.md#iwconfig) — Configura interfaces WiFi antiguas (WEP/WPA1).  
- [`nmcli`](./docs/herramientas.md#nmcli) — CLI para configurar NetworkManager.  
- [`nmtui`](./docs/herramientas.md#nmtui) — Interfaz visual para configurar red.  
- [`resolvectl status`](./docs/herramientas.md#resolvectl-status) — Diagnóstico DNS (systemd-resolved).

---

## 📡 Escaneo y análisis de red

- [`arp -a`](./docs/escaneo.md#arp-a) — Tabla ARP del sistema.  
- [`ip neigh`](./docs/escaneo.md#ip-neigh) — Vecinos de red (similar a arp).  
- [`netstat -tuln`](./docs/escaneo.md#netstat) — Puertos abiertos y servicios escuchando.  
- [`nmap <IP o rango>`](./docs/escaneo.md#nmap) — Escáner de red (puertos, SO, servicios).  
- [`ss -tuln`](./docs/escaneo.md#ss) — Alternativa moderna a netstat.  
- [`tcpdump -i <interfaz>`](./docs/escaneo.md#tcpdump) — Sniffer de paquetes muy potente.  
- [`wireshark`](./docs/escaneo.md#wireshark) — Interfaz gráfica para captura y análisis.

---

## 📄 Logs importantes para analizar errores

- [`cat /var/log/messages`](./docs/logs.md#var-log-messages) — Logs generales.  
- [`cat /var/log/syslog | grep -i network`](./docs/logs.md#var-log-syslog) — Logs relacionados con red.  
- [`dmesg | grep -i eth`](./docs/logs.md#dmesg) — Mensajes del kernel relacionados con ethernet.  
- [`journalctl -u NetworkManager`](./docs/logs.md#journalctl-networkmanager) — Logs del servicio NetworkManager.

---

## 🛠️ Solución de problemas y reparación

- [`rfkill list`](./docs/reparacion.md#rfkill-list) — Muestra bloqueo de WiFi o Bluetooth.  
- [`sudo dhclient <interfaz>`](./docs/reparacion.md#sudo-dhclient) — Solicita IP vía DHCP para interfaz.  
- [`sudo ethtool <interfaz>`](./docs/reparacion.md#sudo-ethtool) — Configuración hardware (velocidad, duplex).  
- [`sudo ip link set <interfaz> up/down`](./docs/reparacion.md#sudo-ip-link-set) — Activa o desactiva interfaz.  
- [`sudo lshw -C network`](./docs/reparacion.md#sudo-lshw) — Información detallada del hardware.  
- [`sudo rfkill unblock all`](./docs/reparacion.md#sudo-rfkill-unblock) — Desbloquea todas las interfaces inalámbricas.  
- [`sudo systemctl restart NetworkManager`](./docs/reparacion.md#sudo-systemctl-restart) — Reinicia servicio red (NetworkManager).

---

## 🎯 Trucos útiles y recordatorios

- Ver IP pública:  
  ```bash
  curl ifconfig.me

