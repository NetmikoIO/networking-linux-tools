<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/lshw.md -->

# 🖥️ Comando `lshw`

## 🧾 Descripción

El comando `lshw` (List Hardware) muestra información detallada sobre el hardware del sistema en Linux. Permite conocer detalles de CPU, memoria, discos, buses, tarjetas de red y otros componentes. Es útil para inventario, diagnóstico y soporte técnico.

---

## 🧪 Sintaxis básica

```bash
lshw [opciones]
```

---

## ⚙️ Opciones comunes

| Opción         | Descripción                                                      |
| -------------- | ---------------------------------------------------------------- |
| `-short`       | Muestra un resumen compacto                                      |
| `-class <tipo>`| Muestra solo una clase de hardware (cpu, memory, disk, network)  |
| `-C <tipo>`    | Igual que `-class`                                               |
| `-html`        | Salida en formato HTML                                           |
| `-json`        | Salida en formato JSON                                           |
| `-xml`         | Salida en formato XML                                            |
| `-sanitize`    | Oculta información sensible (seriales, etc.)                     |
| `-businfo`     | Muestra información de buses                                     |
| `-quiet`       | Reduce la verbosidad de la salida                                |

---

## 🧑‍💻 Ejemplos de uso

### 1. Ver información completa del hardware

```bash
sudo lshw
```

### 2. Ver un resumen compacto

```bash
sudo lshw -short
```

### 3. Mostrar solo información de la CPU

```bash
sudo lshw -class cpu
```

### 4. Mostrar solo información de la red

```bash
sudo lshw -C network
```

### 5. Salida en formato HTML

```bash
sudo lshw -html > hardware.html
```

---

## 📤 Salida típica

```
H/W path        Device      Class          Description
=====================================================
/system                      computer      PC genérico
/0                            bus          Motherboard
/0/0                          memory       8GiB System memory
/0/1                          processor    Intel(R) Core(TM) i5-8250U CPU @ 1.60GHz
/0/100/1f.2    sda           disk         256GB SSD
/0/100/1f.3                  multimedia   Audio device
/0/100/1c.2    wlp2s0        network      Wireless interface
```

- **H/W path**: Ruta jerárquica del hardware.
- **Device**: Nombre del dispositivo.
- **Class**: Tipo de componente (cpu, memory, disk, network, etc.).
- **Description**: Descripción del hardware.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para mostrar toda la información.
- Puede no estar instalado por defecto (`sudo apt install lshw`).
- La salida puede ser extensa; usar filtros o formatos para facilitar la lectura.

---

## 📚 Referencias

- [man lshw](https://man7.org/linux/man-pages/man1/lshw.1.html)
- [Wiki Arch Linux: lshw](https://wiki.archlinux.org/title/Lshw)