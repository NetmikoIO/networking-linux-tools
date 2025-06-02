<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/nmcli.md -->

# 🖥️ Comando `nmcli`

## 🧾 Descripción

El comando `nmcli` es una herramienta de línea de comandos para gestionar NetworkManager en sistemas Linux. Permite administrar conexiones de red (Ethernet, Wi-Fi, VPN, etc.), ver el estado de la red, activar/desactivar interfaces y configurar parámetros avanzados sin necesidad de entorno gráfico.

---

## 🧪 Sintaxis básica

```bash
nmcli [opciones] [comando] [argumentos]
```

---

## ⚙️ Comandos y opciones comunes

| Comando/Opción           | Descripción                                                      |
|-------------------------|------------------------------------------------------------------|
| `general`               | Información general del estado de la red                          |
| `device`                | Gestiona dispositivos de red                                      |
| `connection`            | Gestiona conexiones de red                                        |
| `radio`                 | Gestiona radios Wi-Fi y WWAN                                      |
| `networking`            | Activa/desactiva la red globalmente                               |
| `-t`                    | Salida en formato tabular (útil para scripts)                     |
| `-p`                    | Salida en formato legible (pretty)                                |
| `-f <campos>`           | Especifica campos a mostrar                                       |

---

## 🧑‍💻 Ejemplos de uso

### 1. Ver el estado general de la red

```bash
nmcli general status
```

### 2. Listar dispositivos de red

```bash
nmcli device status
```

### 3. Listar conexiones configuradas

```bash
nmcli connection show
```

### 4. Conectar a una red Wi-Fi

```bash
nmcli device wifi connect "MiRedWiFi" password "miclavewifi"
```

### 5. Activar o desactivar una interfaz

```bash
nmcli device connect eth0
nmcli device disconnect eth0
```

### 6. Crear una nueva conexión estática

```bash
nmcli connection add type ethernet ifname eth0 con-name mi-eth0 ip4 192.168.1.100/24 gw4 192.168.1.1
```

### 7. Eliminar una conexión

```bash
nmcli connection delete mi-eth0
```

---

## 📤 Salida típica

```
DEVICE  TYPE      STATE      CONNECTION
eth0    ethernet  conectado  mi-eth0
wlan0   wifi      disponible --
lo      loopback  sin-gestión --
```

- **DEVICE**: Nombre del dispositivo.
- **TYPE**: Tipo de interfaz.
- **STATE**: Estado (conectado, disponible, desconectado, etc.).
- **CONNECTION**: Nombre de la conexión activa o configurada.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para modificar conexiones o interfaces.
- Cambios realizados con `nmcli` afectan la configuración de NetworkManager.
- Es ideal para servidores, scripts y sistemas sin entorno gráfico.

---

## 📚 Referencias

- [man nmcli](https://man7.org/linux/man-pages/man1/nmcli.1.html)
- [Wiki Arch Linux: nmcli](https://wiki.archlinux.org/title/Nmcli)