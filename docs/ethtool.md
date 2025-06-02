<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/ethtool.md -->

# 🛠️ Comando `ethtool`

## 🧾 Descripción

El comando `ethtool` permite consultar y modificar parámetros de interfaces de red Ethernet en sistemas Linux. Es útil para diagnosticar problemas, ajustar velocidad, duplex, autonegociación, y ver estadísticas de la interfaz.

---

## 🧪 Sintaxis básica

```bash
ethtool [opciones] <interfaz>
```

- **interfaz**: Nombre de la interfaz de red (por ejemplo, `eth0`, `enp3s0`).

---

## ⚙️ Opciones comunes

| Opción                | Descripción                                                      |
|---------------------- |-----------------------------------------------------------------|
| `<interfaz>`          | Muestra información general de la interfaz                       |
| `-i <interfaz>`       | Muestra información del driver                                   |
| `-S <interfaz>`       | Muestra estadísticas de la interfaz                             |
| `-s <interfaz> ...`   | Cambia parámetros (velocidad, duplex, autonegociación, etc.)     |
| `-p <interfaz>`       | Hace parpadear el LED de la interfaz                            |
| `-d <interfaz>`       | Muestra información de diagnóstico                              |
| `-g <interfaz>`       | Muestra o ajusta los tamaños de los búferes                     |
| `-a <interfaz>`       | Muestra o ajusta las opciones de pausa                          |

---

## 🧑‍💻 Ejemplos de uso

### 1. Ver información general de la interfaz

```bash
ethtool eth0
```

### 2. Ver información del driver

```bash
ethtool -i eth0
```

### 3. Ver estadísticas de la interfaz

```bash
ethtool -S eth0
```

### 4. Cambiar velocidad y duplex (requiere privilegios)

```bash
sudo ethtool -s eth0 speed 100 duplex full autoneg off
```

### 5. Hacer parpadear el LED de la tarjeta

```bash
sudo ethtool -p eth0
```

---

## 📤 Salida típica

```
Settings for eth0:
	Supported ports: [ TP ]
	Supported link modes:   1000baseT/Full 
	Supported pause frame use: No
	Supports auto-negotiation: Yes
	Advertised link modes:  1000baseT/Full 
	Advertised pause frame use: No
	Advertised auto-negotiation: Yes
	Speed: 1000Mb/s
	Duplex: Full
	Port: Twisted Pair
	PHYAD: 1
	Transceiver: internal
	Auto-negotiation: on
	Link detected: yes
```

- **Speed**: Velocidad de enlace.
- **Duplex**: Modo dúplex (Full/Half).
- **Auto-negotiation**: Autonegociación activada o no.
- **Link detected**: Si la interfaz está conectada.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para modificar parámetros.
- No todas las interfaces soportan todas las opciones.
- Cambios realizados con `ethtool` pueden perderse tras reiniciar la interfaz o el sistema.

---

## 📚 Referencias

- [man ethtool](https://man7.org/linux/man-pages/man8/ethtool.8.html)
- [Wiki Arch Linux: ethtool](https://wiki.archlinux.org/title/Ethtool)