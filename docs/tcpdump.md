<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/tcpdump.md -->

# 📡 Comando `tcpdump`

## 🧾 Descripción

El comando `tcpdump` es una herramienta de línea de comandos para capturar y analizar tráfico de red en tiempo real. Permite inspeccionar paquetes que pasan por una interfaz de red, aplicar filtros avanzados y guardar capturas para su análisis posterior. Es ampliamente utilizado en diagnóstico, auditoría y seguridad de redes.

---

## 🧪 Sintaxis básica

```bash
tcpdump [opciones] [expresión de filtro]
```

---

## ⚙️ Opciones comunes

| Opción                | Descripción                                                      |
|---------------------- |-----------------------------------------------------------------|
| `-i <interfaz>`       | Especifica la interfaz de red a capturar                         |
| `-n`                  | No resuelve nombres de host o puertos                            |
| `-v`, `-vv`, `-vvv`   | Aumenta el nivel de detalle de la salida                         |
| `-c <n>`              | Captura solo `n` paquetes                                        |
| `-w <archivo>`        | Guarda la captura en un archivo (formato pcap)                   |
| `-r <archivo>`        | Lee paquetes desde un archivo pcap                               |
| `-s <bytes>`          | Tamaño del snaplen (porción de cada paquete a capturar)           |
| `-tt`                 | Muestra marcas de tiempo en formato absoluto                     |
| `-A`                  | Muestra los datos en ASCII                                       |
| `-X`                  | Muestra los datos en hexadecimal y ASCII                         |

---

## 🧑‍💻 Ejemplos de uso

### 1. Capturar tráfico en la interfaz principal

```bash
sudo tcpdump -i eth0
```

### 2. Capturar solo 10 paquetes

```bash
sudo tcpdump -i eth0 -c 10
```

### 3. Guardar la captura en un archivo para Wireshark

```bash
sudo tcpdump -i eth0 -w captura.pcap
```

### 4. Leer y analizar un archivo de captura

```bash
tcpdump -r captura.pcap
```

### 5. Filtrar tráfico HTTP

```bash
sudo tcpdump -i eth0 tcp port 80
```

### 6. Mostrar datos en hexadecimal y ASCII

```bash
sudo tcpdump -X -i eth0
```

---

## 📤 Salida típica

```
10:00:00.000000 IP 192.168.1.100.54321 > 93.184.216.34.80: Flags [S], seq 123456, win 64240, length 0
10:00:00.100000 IP 93.184.216.34.80 > 192.168.1.100.54321: Flags [S.], seq 654321, ack 123457, win 65535, length 0
```

- **IP origen > destino**: Dirección y puerto de origen y destino.
- **Flags**: Indicadores TCP (S = SYN, F = FIN, P = PUSH, etc.).
- **seq/ack**: Números de secuencia y acuse de recibo.
- **length**: Tamaño del paquete.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para capturar en la mayoría de interfaces.
- El uso de filtros reduce la cantidad de datos y mejora el análisis.
- Los archivos `.pcap` pueden analizarse con Wireshark u otras herramientas.
- El análisis de tráfico puede exponer información sensible; úsalo con responsabilidad.

---

## 📚 Referencias

- [man tcpdump](https://man7.org/linux/man-pages/man8/tcpdump.8.html)
- [Wiki Arch Linux: tcpdump](https://wiki.archlinux.org/title/Tcpdump)