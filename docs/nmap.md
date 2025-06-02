<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/nmap.md -->

# 🔍 Comando `nmap`

## 🧾 Descripción

El comando `nmap` (Network Mapper) es una herramienta de código abierto para escaneo y auditoría de redes. Permite descubrir hosts, servicios, puertos abiertos, sistemas operativos y vulnerabilidades en redes locales o remotas. Es ampliamente utilizado en administración de sistemas, seguridad informática y pruebas de penetración.

---

## 🧪 Sintaxis básica

```bash
nmap [opciones] <objetivo>
```

- **objetivo**: IP, rango de IPs, dominio o subred a analizar.

---

## ⚙️ Opciones comunes

| Opción         | Descripción                                                      |
| -------------- | ---------------------------------------------------------------- |
| `-sS`          | Escaneo SYN (rápido y sigiloso, "half-open")                    |
| `-sT`          | Escaneo TCP completo                                             |
| `-sU`          | Escaneo de puertos UDP                                           |
| `-p <puertos>` | Especifica puertos o rangos a escanear                           |
| `-A`           | Detección de SO, servicios y scripts avanzados                   |
| `-O`           | Detección de sistema operativo                                   |
| `-sV`          | Detección de versiones de servicios                              |
| `-Pn`          | No hace ping previo (asume host activo)                          |
| `-T<0-5>`      | Ajusta velocidad/agresividad del escaneo                         |
| `-oN <archivo>`| Guarda el resultado en un archivo de texto                       |
| `-oX <archivo>`| Guarda el resultado en formato XML                               |
| `-v`           | Modo detallado (verbose)                                         |

---

## 🧑‍💻 Ejemplos de uso

### 1. Escaneo rápido de puertos comunes

```bash
nmap scanme.nmap.org
```

### 2. Escaneo de puertos específicos

```bash
nmap -p 22,80,443 192.168.1.1
```

### 3. Escaneo completo de todos los puertos

```bash
nmap -p- 192.168.1.1
```

### 4. Detección de sistema operativo y servicios

```bash
sudo nmap -A 192.168.1.1
```

### 5. Escaneo de una subred completa

```bash
nmap 192.168.1.0/24
```

### 6. Guardar resultados en un archivo

```bash
nmap -oN resultado.txt 192.168.1.1
```

---

## 📤 Salida típica

```
Starting Nmap 7.80 ( https://nmap.org ) at 2025-06-02 10:00 UTC
Nmap scan report for 192.168.1.1
Host is up (0.0010s latency).
Not shown: 997 closed ports
PORT    STATE SERVICE
22/tcp  open  ssh
80/tcp  open  http
443/tcp open  https

Nmap done: 1 IP address (1 host up) scanned in 1.23 seconds
```

- **PORT**: Puerto detectado.
- **STATE**: Estado del puerto (open, closed, filtered).
- **SERVICE**: Servicio identificado en el puerto.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para ciertos tipos de escaneo.
- El uso de `nmap` en redes ajenas puede ser considerado intrusivo o ilegal.
- Algunos sistemas pueden detectar y bloquear escaneos.

---

## 📚 Referencias

- [man nmap](https://man7.org/linux/man-pages/man1/nmap.1.html)
- [Sitio oficial de Nmap](https://nmap.org/)
- [Wiki Arch Linux: nmap](https://wiki.archlinux.org/title/Nmap)