<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/dhclient.md -->

# 🌐 Comando `dhclient`

## 🧾 Descripción

El comando `dhclient` es un cliente DHCP para sistemas Linux. Se utiliza para solicitar y gestionar la configuración de red (dirección IP, puerta de enlace, DNS, etc.) de manera automática desde un servidor DHCP. Es fundamental para la administración dinámica de redes.

---

## 🧪 Sintaxis básica

```bash
dhclient [opciones] [interfaz]
```

- **interfaz**: Nombre de la interfaz de red (por ejemplo, `eth0`, `enp3s0`, `wlan0`).

---

## ⚙️ Opciones comunes

| Opción         | Descripción                                                      |
| -------------- | ---------------------------------------------------------------- |
| `-v`           | Modo detallado (verbose), muestra información del proceso         |
| `-r`           | Libera la dirección IP obtenida por DHCP                         |
| `-1`           | Realiza solo un intento de obtener una concesión DHCP            |
| `-4`           | Fuerza el uso de DHCP sobre IPv4                                 |
| `-6`           | Fuerza el uso de DHCP sobre IPv6                                 |
| `-pf <archivo>`| Especifica el archivo de PID                                     |
| `-lf <archivo>`| Especifica el archivo de lease                                   |
| `-sf <script>` | Especifica el script a ejecutar cuando cambia la configuración   |

---

## 🧑‍💻 Ejemplos de uso

### 1. Solicitar una IP para una interfaz específica

```bash
sudo dhclient eth0
```

### 2. Liberar la IP de una interfaz

```bash
sudo dhclient -r eth0
```

### 3. Solicitar una IP mostrando información detallada

```bash
sudo dhclient -v wlan0
```

### 4. Solicitar una IP solo para IPv6

```bash
sudo dhclient -6 eth0
```

---

## 📤 Salida típica

```
Internet Systems Consortium DHCP Client 4.4.1
Copyright 2004-2018 Internet Systems Consortium.
All rights reserved.
Listening on LPF/eth0/00:11:22:33:44:55
Sending on   LPF/eth0/00:11:22:33:44:55
DHCPDISCOVER on eth0 to 255.255.255.255 port 67 interval 3
DHCPOFFER from 192.168.1.1
DHCPREQUEST on eth0 to 255.255.255.255 port 67
DHCPACK from 192.168.1.1
bound to 192.168.1.100 -- renewal in 3600 seconds.
```

- **DHCPDISCOVER**: Solicitud de IP al servidor DHCP.
- **DHCPOFFER**: Oferta de IP recibida.
- **DHCPREQUEST**: Solicitud de concesión de IP.
- **DHCPACK**: Confirmación de concesión.
- **bound to ...**: IP asignada a la interfaz.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario (`sudo`) para modificar la configuración de red.
- Puede interrumpir la conectividad de red temporalmente al renovar o liberar la IP.
- En sistemas modernos, puede ser reemplazado por NetworkManager o `systemd-networkd`.
- Los archivos de configuración suelen estar en `/etc/dhcp/`.

---

## 📚 Referencias

- [man dhclient](https://man7.org/linux/man-pages/man8/dhclient.8.html)
- [Wikipedia: DHCP](https://es.wikipedia.org/wiki/Dynamic_Host_Configuration_Protocol)