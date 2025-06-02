# Networking Linux Tools

Repositorio con comandos esenciales para análisis, configuración y reparación de redes en Linux.  
Ideal para técnicos y administradores que necesitan un kit rápido y confiable.

---

## Índice automático

- [Comandos básicos de diagnóstico](#comandos-básicos-de-diagnóstico)
- [Escaneo y análisis de red](#escaneo-y-análisis-de-red)
- [Herramientas de configuración y comprobación](#herramientas-de-configuración-y-comprobación)
- [Logs importantes para analizar errores](#logs-importantes-para-analizar-errores)
- [Solución de problemas y reparación](#solución-de-problemas-y-reparación)
- [Trucos útiles y recordatorios](#trucos-útiles-y-recordatorios)

---

## Comandos básicos de diagnóstico

| Comando                      | Descripción práctica                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------|
| [dig](./docs/dig.md)               | Consulta DNS avanzada, fundamental para diagnosticar problemas de resolución de nombres.          |
| [host](./docs/host.md)              | Resuelve nombres DNS y muestra información simple sobre dominios.                                |
| [ip](./docs/ip.md)                | Muestra interfaces y rutas, básico para conocer el estado y configuración actual de red.          |
| [mtr](./docs/mtr.md)               | Diagnóstico dinámico y continuo de ruta, mezcla ping y traceroute, ideal para análisis en tiempo real. |
| [nslookup](./docs/nslookup.md)           | Consulta DNS básica, rápida para verificar la IP de un dominio o viceversa.                      |
| [ping](./docs/ping.md)              | Verifica si otro host responde, básico para comprobar conectividad y latencia.                   |
| [traceroute](./docs/traceroute.md)        | Muestra ruta y saltos de paquetes, útil para detectar dónde se pierde la conexión.               |
| [whois](./docs/whois.md)             | Obtiene información del registrante de dominio/IP, útil para investigación y auditoría.        |

---

## Escaneo y análisis de red

| Comando                       | Descripción práctica                                                                           |
|-------------------------------|-----------------------------------------------------------------------------------------------|
| [arp -a](./docs/arp.md)                   | Muestra tabla ARP, ayuda a detectar problemas de resolución MAC-IP en la red local.          |
| [ip neigh](./docs/ip.md)                      | Similar a arp, muestra vecinos y caché ARP, útil para diagnósticos rápidos.                  |
| [nmap <IP o rango>](./docs/nmap.md)                 | Escáner de puertos y servicios, para auditorías de seguridad y descubrimiento de hosts.      |
| [netstat -tuln](./docs/netstat.md)           | Lista puertos abiertos y servicios escuchando, para auditar servicios activos.               |
| [ss -tuln](./docs/ss.md)                  | Versión moderna y más rápida que netstat para mostrar conexiones y puertos abiertos.         |
| [tcpdump -i <interfaz>](./docs/tcpdump.md)             | Captura y análisis de tráfico en red, imprescindible para análisis profundo de paquetes.    |
| [wireshark](./docs/wireshark.md)               | Interfaz gráfica para capturar y analizar tráfico, potente y fácil para técnicos con GUI.     |

---

## Herramientas de configuración y comprobación

| Comando                      | Descripción práctica                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------|
| [cat /etc/resolv.conf](./docs/resolv.conf.md) | Archivo clásico con servidores DNS, ideal para verificar configuraciones DNS.               |
| [ifconfig](./docs/ifconfig.md)           | Comando clásico para mostrar/configurar interfaces, todavía útil en sistemas legacy.        |
| [iwconfig](./docs/iwconfig.md)            | Configura interfaces WiFi antiguas, para redes inalámbricas básicas (WEP/WPA1).             |
| [nmcli](./docs/nmcli.md)                | CLI potente para manejar NetworkManager, configurar conexiones y dispositivos.              |
| [nmtui](./docs/nmtui.md)                | Interfaz textual para configuración rápida y visual de conexiones en distros con NM.        |
| [resolvectl](./docs/resolvectl.md)          | Diagnóstico y control avanzado de DNS con systemd-resolved, imprescindible en sistemas modernos. |

---

## Logs importantes para analizar errores

| Archivo / Comando                    | Descripción práctica                                                      |
|------------------------------------|--------------------------------------------------------------------------|
| `cat /var/log/messages`             | Logs generales de eventos del sistema, dependiendo de la distro.        |
| `cat /var/log/syslog | grep -i network` | Logs generales del sistema filtrados para red, muy útil para debugging.   |
| `dmesg | grep -i eth`               | Muestra mensajes del kernel relacionados con interfaces Ethernet.       |
| `journalctl -u NetworkManager`      | Logs detallados del gestor de red NetworkManager.                        |

---

## Solución de problemas y reparación

| Comando                          | Descripción práctica                                                                          |
|----------------------------------|----------------------------------------------------------------------------------------------|
| [sudo dhclient <interfaz>](./docs/dhclient.md)              | Solicita o renueva una IP vía DHCP para una interfaz, útil si no se obtiene IP automática.  |
| [sudo ethtool <interfaz>](./docs/ethtool.md)                | Muestra y cambia parámetros físicos (velocidad, duplex), esencial para problemas de hardware. |
| [sudo ip link set <interfaz> up/down](./docs/ip.md)          | Activa o desactiva una interfaz física, importante para reiniciar la conexión sin reboot.   |
| [sudo lshw -C network](./docs/lshw.md)                      | Información detallada del hardware de red, ayuda a diagnosticar fallos físicos o drivers.   |
| [sudo rfkill unblock all](./docs/rfkill.md)                 | Desbloquea todas las interfaces inalámbricas, solución rápida para errores por bloqueo.    |
| [rfkill list](./docs/rfkill.md)                            | Muestra si WiFi o Bluetooth están bloqueados, causa común de desconexiones inalámbricas.    |
| [sudo systemctl restart NetworkManager](./docs/systemctl.md) | Reinicia el gestor de red, paso común para solucionar problemas de conexión.                |

---

## Trucos útiles y recordatorios

- **Ver IP pública rápidamente:**  
  ```bash
  curl ifconfig.me
