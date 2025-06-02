<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/arp.md -->

# 🗂️ Comando `arp`

## 🧾 Descripción

El comando `arp` (Address Resolution Protocol) permite ver y manipular la caché ARP del sistema. La caché ARP almacena las asociaciones entre direcciones IP y direcciones MAC de los dispositivos en la red local. Es útil para diagnosticar problemas de red y para tareas de administración avanzada.

---

## 🧪 Sintaxis básica

```bash
arp [opciones]
```

---

## ⚙️ Opciones comunes

| Opción         | Descripción                                              |
| -------------- | -------------------------------------------------------- |
| `-a`           | Muestra todas las entradas de la caché ARP              |
| `-n`           | Muestra direcciones IP en formato numérico               |
| `-d <IP>`      | Elimina la entrada ARP para la IP especificada           |
| `-s <IP> <MAC>`| Añade una entrada estática a la caché ARP                |
| `-v`           | Muestra información detallada (verbose)                  |

> **Nota:** En sistemas modernos, el comando `arp` puede estar obsoleto y reemplazado por `ip neigh`.

---

## 🧑‍💻 Ejemplos de uso

### 1. Ver la tabla ARP actual

```bash
arp -a
```

### 2. Ver la tabla ARP con direcciones numéricas

```bash
arp -an
```

### 3. Eliminar una entrada ARP

```bash
sudo arp -d 192.168.1.10
```

### 4. Añadir una entrada ARP estática

```bash
sudo arp -s 192.168.1.50 00:11:22:33:44:55
```

---

## 📤 Salida típica

```
Address                  HWtype  HWaddress           Flags Mask            Iface
192.168.1.1              ether   00:11:22:33:44:aa   C                     eth0
192.168.1.10             ether   00:11:22:33:44:bb   C                     eth0
```

- **Address**: Dirección IP del host.
- **HWtype**: Tipo de hardware (normalmente `ether` para Ethernet).
- **HWaddress**: Dirección MAC asociada.
- **Flags**: Estado de la entrada (`C` = completa, `M` = publicada manualmente).
- **Iface**: Interfaz de red.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para modificar la caché ARP.
- El uso incorrecto puede causar problemas de conectividad en la red local.
- En sistemas modernos, se recomienda usar `ip neigh` para gestionar la tabla ARP.

---

## 📚 Referencias

- [man arp](https://man7.org/linux/man-pages/man8/arp.8.html)
- [Wikipedia: ARP](https://es.wikipedia.org/wiki/Address_Resolution_Protocol)