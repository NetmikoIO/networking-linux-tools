<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/traceroute.md -->

# 🌍 Comando `traceroute`

## 🧾 Descripción

El comando `traceroute` permite rastrear la ruta que siguen los paquetes desde el equipo local hasta un destino (host o IP) a través de la red. Muestra cada salto intermedio (router/gateway) y mide la latencia de cada uno, ayudando a diagnosticar problemas de conectividad y cuellos de botella en la red.

---

## 🧪 Sintaxis básica

```bash
traceroute [opciones] <host o IP>
```

- **host o IP**: Destino a analizar (dominio o dirección IP).

---

## ⚙️ Opciones comunes

| Opción         | Descripción                                                      |
| -------------- | ---------------------------------------------------------------- |
| `-n`           | No resuelve nombres de host, muestra solo direcciones IP          |
| `-m <saltos>`  | Número máximo de saltos (TTL)                                    |
| `-w <seg>`     | Tiempo de espera por respuesta de cada salto                     |
| `-q <n>`       | Número de consultas por salto                                    |
| `-I`           | Usa paquetes ICMP ECHO en vez de UDP                             |
| `-T`           | Usa paquetes TCP SYN                                             |
| `-4`           | Fuerza el uso de IPv4                                            |
| `-6`           | Fuerza el uso de IPv6                                            |

---

## 🧑‍💻 Ejemplos de uso

### 1. Rastrear la ruta a un dominio

```bash
traceroute google.com
```

### 2. Mostrar solo direcciones IP

```bash
traceroute -n 8.8.8.8
```

### 3. Limitar el número de saltos a 10

```bash
traceroute -m 10 example.com
```

### 4. Usar paquetes ICMP (como Windows)

```bash
sudo traceroute -I google.com
```

### 5. Forzar IPv6

```bash
traceroute -6 ipv6.google.com
```

---

## 📤 Salida típica

```
traceroute to google.com (142.250.184.206), 30 hops max, 60 byte packets
 1  192.168.1.1  1.123 ms  1.045 ms  1.012 ms
 2  10.0.0.1     5.234 ms  5.201 ms  5.198 ms
 3  8.8.8.8     20.345 ms 20.301 ms 20.298 ms
 ...
```

- Cada línea representa un salto (router/gateway) en la ruta.
- Los valores en ms indican la latencia de cada intento.
- Un `*` indica que no hubo respuesta para ese intento.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para ciertas opciones (ICMP, TCP).
- Algunos routers pueden bloquear o limitar respuestas, mostrando `*` en la salida.
- El comando puede no estar instalado por defecto (`traceroute` o `inetutils-traceroute`).

---

## 📚 Referencias

- [man traceroute](https://man7.org/linux/man-pages/man8/traceroute.8.html)
- [Wiki Arch Linux: traceroute](https://wiki.archlinux.org/title/Traceroute)