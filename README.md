# Networking Linux Tools

Repositorio con documentación organizada sobre comandos y herramientas esenciales para administración, diagnóstico y solución de problemas de red en Linux.

---

## Índice de comandos

### 🔍 1. Comandos básicos para diagnóstico y consulta

| Comando                | Descripción                                                    |
|------------------------|----------------------------------------------------------------|
| [ping](./docs/ping.md)             | Verifica conectividad con otro host.                          |
| [traceroute](./docs/traceroute.md)     | Muestra la ruta que siguen los paquetes.                      |
| [mtr](./docs/mtr.md)               | Diagnóstico continuo de red (mejor que traceroute).           |
| [dig](./docs/dig.md)               | Consulta DNS detallada.                                        |
| [nslookup](./docs/nslookup.md)           | Consulta DNS básica.                                           |
| [host](./docs/host.md)              | Resolución de nombre DNS.                                      |
| [whois](./docs/whois.md)             | Información del dominio o IP (registrante, etc).              |
| [ip](./docs/ip.md)                 | Muestra interfaces, direcciones y rutas.                      |
| [nmcli](./docs/nmcli.md)              | Estado de interfaces con NetworkManager.                      |

### 🛠️ 2. Solución de problemas y reparación

| Comando                                | Descripción                                                  |
|----------------------------------------|--------------------------------------------------------------|
| [sudo systemctl restart NetworkManager](./docs/systemctl.md) | Reinicia el servicio de red en distros con NetworkManager.   |
| [sudo dhclient](./docs/dhclient.md)                   | Solicita una IP vía DHCP para una interfaz.                  |
| [sudo ip link set](./docs/ip.md)              | Activa o desactiva una interfaz de red.                      |
| [sudo ethtool](./docs/ethtool.md)                 | Muestra o cambia configuración de hardware.                  |
| [sudo lshw -C network](./docs/lshw.md)            | Información detallada del hardware de red.                   |
| [rfkill list](./docs/rfkill.md)                   | Muestra si el WiFi o Bluetooth está bloqueado.               |
| [sudo rfkill unblock all](./docs/rfkill.md)         | Desbloquea todas las interfaces inalámbricas.                |

### 📡 3. Escaneo y análisis de red

| Comando                      | Descripción                                                |
|------------------------------|------------------------------------------------------------|
| [netstat -tuln](./docs/netstat.md)             | Muestra puertos abiertos y servicios escuchando.           |
| [ss -tuln](./docs/ss.md)                    | Alternativa moderna a netstat.                              |
| [tcpdump -i <interfaz>](./docs/tcpdump.md)           | Sniffer de paquetes, muy potente.                           |
| [wireshark](./docs/wireshark.md)                | Interfaz gráfica para captura y análisis de paquetes.       |
| [nmap](./docs/nmap.md)                     | Escáner de red (puertos abiertos, SO, servicios).           |
| [arp -a](./docs/arp.md)                     | Tabla ARP del sistema.                                      |
| [ip neigh](./docs/ip.md)                    | Similar a arp -a, muestra vecinos de red.                   |

### 🧰 4. Herramientas de configuración y comprobación

| Comando                    | Descripción                                             |
|----------------------------|---------------------------------------------------------|
| [ifconfig](./docs/ifconfig.md)               | Obsoleto pero aún útil en algunos sistemas antiguos.      |
| [iwconfig](./docs/iwconfig.md)               | Configura interfaces WiFi (antiguo).                      |
| [nmcli](./docs/nmcli.md)                    | CLI de NetworkManager para configurar conexiones.       |
| [nmtui](./docs/nmtui.md)                    | Interfaz TUI para configurar red (más visual).           |
| [resolvectl status](./docs/resolvectl.md)           | Diagnóstico de resolución DNS (en systemd-resolved).       |
| [cat /etc/resolv.conf](./docs/resolv.conf.md)       | Verifica qué servidores DNS se están usando.              |

### 📄 5. Logs importantes para analizar errores

| Archivo / Comando                           | Descripción                                   |
|--------------------------------------------|-----------------------------------------------|
| `dmesg | grep -i eth`                      | Logs del kernel relacionados con interfaces. |
| `journalctl -u NetworkManager`              | Logs de NetworkManager.                        |
| `cat /var/log/syslog | grep -i network`    | Logs generales en Debian/Ubuntu.               |
| `cat /var/log/messages`                     | Logs generales en otras distribuciones.       |

---

### 🎯 Trucos útiles y recordatorios

- **Ver IP pública:**

```bash
curl ifconfig.me
```


