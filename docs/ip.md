<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/ip.md -->

# 🌐 Comando `ip`

## 🧾 Descripción

El comando `ip` es la herramienta moderna para gestionar interfaces de red, rutas, direcciones y otros parámetros de red en sistemas Linux. Reemplaza a utilidades más antiguas como `ifconfig`, `route` y `arp`, ofreciendo mayor flexibilidad y funcionalidad.

---

## 🧪 Sintaxis básica

```bash
ip [objeto] [acción] [parámetros]
```

- **objeto**: Elemento a gestionar (`link`, `addr`, `route`, `neigh`, etc.).
- **acción**: Operación a realizar (`show`, `add`, `del`, `flush`, etc.).

---

## ⚙️ Objetos y acciones comunes

| Objeto      | Acción/Descripción                                              |
|-------------|-----------------------------------------------------------------|
| `link`      | Gestiona interfaces de red                                      |
| `addr`      | Gestiona direcciones IP                                         |
| `route`     | Gestiona rutas de red                                           |
| `neigh`     | Gestiona la caché ARP/NDP                                       |
| `maddr`     | Gestiona direcciones multicast                                  |
| `rule`      | Gestiona reglas de enrutamiento                                 |

---

## 🧑‍💻 Ejemplos de uso

### 1. Ver todas las interfaces de red

```bash
ip link show
```

### 2. Ver direcciones IP asignadas

```bash
ip addr show
```

### 3. Asignar una IP a una interfaz

```bash
sudo ip addr add 192.168.1.100/24 dev eth0
```

### 4. Activar o desactivar una interfaz

```bash
sudo ip link set eth0 up
sudo ip link set eth0 down
```

### 5. Ver la tabla de rutas

```bash
ip route show
```

### 6. Añadir una ruta estática

```bash
sudo ip route add 192.168.2.0/24 via 192.168.1.1 dev eth0
```

### 7. Ver la caché ARP

```bash
ip neigh show
```

---

## 📤 Salida típica

```
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP mode DEFAULT group default qlen 1000
    link/ether 00:11:22:33:44:55 brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.100/24 brd 192.168.1.255 scope global eth0
       valid_lft forever preferred_lft forever
```

- **link/ether**: Dirección MAC de la interfaz.
- **inet**: Dirección IPv4 asignada.
- **mtu**: Tamaño máximo de unidad de transmisión.
- **state UP/DOWN**: Estado de la interfaz.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para modificar la configuración de red.
- Es la herramienta recomendada en sistemas modernos; `ifconfig` y otros están obsoletos.
- La sintaxis puede parecer compleja, pero es muy poderosa y flexible.

---

## 📚 Referencias

- [man ip](https://man7.org/linux/man-pages/man8/ip.8.html)
- [Wiki Arch Linux: ip](https://wiki.archlinux.org/title/Ip_(utilidad))