<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/netstat.md -->

# 📊 Comando `netstat`

## 🧾 Descripción

El comando `netstat` (network statistics) muestra información sobre conexiones de red, tablas de enrutamiento, estadísticas de interfaces, conexiones activas y puertos en escucha. Es útil para diagnosticar problemas de red, monitorear tráfico y detectar servicios activos.

> **Nota:** En sistemas modernos, `netstat` ha sido reemplazado por `ss`, pero sigue siendo ampliamente utilizado y conocido.

---

## 🧪 Sintaxis básica

```bash
netstat [opciones]
```

---

## ⚙️ Opciones comunes

| Opción         | Descripción                                                      |
| -------------- | ---------------------------------------------------------------- |
| `-a`           | Muestra todas las conexiones y puertos en escucha                 |
| `-t`           | Muestra solo conexiones TCP                                      |
| `-u`           | Muestra solo conexiones UDP                                      |
| `-l`           | Solo puertos en escucha                                          |
| `-n`           | Muestra direcciones y puertos en formato numérico                |
| `-p`           | Muestra el PID y nombre del programa asociado                    |
| `-r`           | Muestra la tabla de enrutamiento                                 |
| `-i`           | Muestra estadísticas de interfaces de red                        |
| `-s`           | Muestra estadísticas resumidas por protocolo                     |

---

## 🧑‍💻 Ejemplos de uso

### 1. Ver todas las conexiones y puertos en escucha

```bash
netstat -a
```

### 2. Ver conexiones TCP activas

```bash
netstat -at
```

### 3. Ver puertos en escucha y el proceso asociado

```bash
sudo netstat -tulnp
```

### 4. Ver la tabla de enrutamiento

```bash
netstat -r
```

### 5. Ver estadísticas de interfaces de red

```bash
netstat -i
```

---

## 📤 Salida típica

```
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
 tcp        0      0 0.0.0.0:22            0.0.0.0:*               LISTEN      1234/sshd
 tcp        0      0 192.168.1.100:54321   93.184.216.34:80        ESTABLISHED 2345/firefox
 udp        0      0 0.0.0.0:68            0.0.0.0:*                           5678/dhclient
```

- **Proto**: Protocolo (TCP/UDP).
- **Local Address**: Dirección y puerto local.
- **Foreign Address**: Dirección y puerto remoto.
- **State**: Estado de la conexión (LISTEN, ESTABLISHED, etc.).
- **PID/Program name**: Proceso asociado (si se usa `-p`).

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para mostrar información de todos los procesos.
- Puede no estar instalado por defecto (`net-tools`).
- Para nuevas implementaciones, se recomienda usar `ss`.

---

## 📚 Referencias

- [man netstat](https://man7.org/linux/man-pages/man8/netstat.8.html)
- [Wiki Arch Linux: netstat](https://wiki.archlinux.org/title/Netstat)