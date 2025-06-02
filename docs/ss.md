<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/ss.md -->

# 📊 Comando `ss`

## 🧾 Descripción

El comando `ss` (socket statistics) es la herramienta moderna para mostrar información sobre conexiones de red, sockets, puertos en escucha, estadísticas de protocolos y más en sistemas Linux. Es más rápido y flexible que `netstat` y es recomendado en sistemas actuales.

---

## 🧪 Sintaxis básica

```bash
ss [opciones]
```

---

## ⚙️ Opciones comunes

| Opción         | Descripción                                                      |
| -------------- | ---------------------------------------------------------------- |
| `-t`           | Muestra solo conexiones TCP                                      |
| `-u`           | Muestra solo conexiones UDP                                      |
| `-l`           | Solo sockets en escucha                                          |
| `-a`           | Muestra todas las conexiones y sockets                           |
| `-n`           | Muestra direcciones y puertos en formato numérico                |
| `-p`           | Muestra el proceso asociado a cada socket                        |
| `-r`           | Muestra la tabla de enrutamiento                                 |
| `-s`           | Muestra estadísticas resumidas                                   |
| `-o`           | Muestra información adicional de temporizadores                   |
| `-4`           | Solo IPv4                                                        |
| `-6`           | Solo IPv6                                                        |

---

## 🧑‍💻 Ejemplos de uso

### 1. Ver todas las conexiones y sockets en escucha

```bash
ss -a
```

### 2. Ver conexiones TCP activas

```bash
ss -t
```

### 3. Ver puertos en escucha y el proceso asociado

```bash
sudo ss -tulnp
```

### 4. Ver la tabla de enrutamiento

```bash
ss -r
```

### 5. Ver estadísticas resumidas de sockets

```bash
ss -s
```

---

## 📤 Salida típica

```
State      Recv-Q Send-Q Local Address:Port  Peer Address:Port Process
LISTEN     0      128    0.0.0.0:22         0.0.0.0:*         users:("sshd",pid=1234,fd=3)
ESTAB      0      0      192.168.1.100:54321 93.184.216.34:80 users:("firefox",pid=2345,fd=45)
```

- **State**: Estado de la conexión (LISTEN, ESTAB, etc.).
- **Local Address:Port**: Dirección y puerto local.
- **Peer Address:Port**: Dirección y puerto remoto.
- **Process**: Proceso asociado (si se usa `-p`).

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para mostrar información de todos los procesos.
- Es la herramienta recomendada en sistemas modernos en lugar de `netstat`.
- Permite filtrar y mostrar información muy detallada sobre sockets y conexiones.

---

## 📚 Referencias

- [man ss](https://man7.org/linux/man-pages/man8/ss.8.html)
- [Wiki Arch Linux: ss](https://wiki.archlinux.org/title/Ss)