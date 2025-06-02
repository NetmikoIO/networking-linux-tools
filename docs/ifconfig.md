<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/ifconfig.md -->

# 🖧 Comando `ifconfig`

## 🧾 Descripción

El comando `ifconfig` (interface configuration) se utiliza para ver y configurar interfaces de red en sistemas Linux y Unix. Permite asignar direcciones IP, activar o desactivar interfaces, y ver información sobre el estado de la red. Aunque ha sido reemplazado en muchos sistemas modernos por el comando `ip`, sigue siendo útil y ampliamente utilizado.

---

## 🧪 Sintaxis básica

```bash
ifconfig [interfaz] [opciones]
```

- **interfaz**: Nombre de la interfaz de red (por ejemplo, `eth0`, `wlan0`).

---

## ⚙️ Opciones comunes

| Opción                | Descripción                                                      |
|---------------------- |-----------------------------------------------------------------|
| (sin argumentos)      | Muestra todas las interfaces activas                             |
| `<interfaz>`          | Muestra información de una interfaz específica                   |
| `up`                  | Activa la interfaz                                              |
| `down`                | Desactiva la interfaz                                           |
| `inet <IP>`           | Asigna una dirección IPv4 a la interfaz                         |
| `netmask <máscara>`   | Especifica la máscara de red                                    |
| `broadcast <IP>`      | Especifica la dirección de broadcast                            |
| `mtu <valor>`         | Cambia el tamaño máximo de unidad de transmisión                |
| `hw ether <MAC>`      | Cambia la dirección MAC de la interfaz                          |
| `promisc`             | Activa el modo promiscuo                                        |

---

## 🧑‍💻 Ejemplos de uso

### 1. Ver todas las interfaces de red

```bash
ifconfig
```

### 2. Ver información de una interfaz específica

```bash
ifconfig eth0
```

### 3. Asignar una IP y máscara a una interfaz

```bash
sudo ifconfig eth0 192.168.1.100 netmask 255.255.255.0
```

### 4. Activar o desactivar una interfaz

```bash
sudo ifconfig eth0 up
sudo ifconfig eth0 down
```

### 5. Cambiar la dirección MAC de una interfaz

```bash
sudo ifconfig eth0 hw ether 00:11:22:33:44:55
```

---

## 📤 Salida típica

```
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.1.100  netmask 255.255.255.0  broadcast 192.168.1.255
        inet6 fe80::211:22ff:fe33:4455  prefixlen 64  scopeid 0x20<link>
        ether 00:11:22:33:44:55  txqueuelen 1000  (Ethernet)
        RX packets 1000  bytes 123456 (123.4 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 800  bytes 654321 (654.3 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

- **inet**: Dirección IPv4 asignada.
- **netmask**: Máscara de red.
- **broadcast**: Dirección de broadcast.
- **ether**: Dirección MAC.
- **RX/TX packets**: Paquetes recibidos/enviados.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para modificar interfaces.
- En sistemas modernos, se recomienda usar el comando `ip` en lugar de `ifconfig`.
- Puede no estar instalado por defecto (`net-tools`).

---

## 📚 Referencias

- [man ifconfig](https://man7.org/linux/man-pages/man8/ifconfig.8.html)
- [Wiki Arch Linux: ifconfig](https://wiki.archlinux.org/title/Ifconfig)