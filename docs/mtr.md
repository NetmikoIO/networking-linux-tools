<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/mtr.md -->

# 🌐 Comando `mtr`

## 🧾 Descripción

El comando `mtr` (My Traceroute) combina las funcionalidades de `traceroute` y `ping` para diagnosticar la conectividad de red. Proporciona información en tiempo real sobre la ruta que siguen los paquetes hasta un destino, mostrando latencia, pérdida de paquetes y estadísticas de cada salto.

---

## 🧪 Sintaxis básica

```bash
mtr [opciones] <host o IP>
```

- **host o IP**: Destino a analizar (dominio o dirección IP).

---

## ⚙️ Opciones comunes

| Opción         | Descripción                                                      |
| -------------- | ---------------------------------------------------------------- |
| `-r`           | Modo reporte (salida en texto plano, ideal para scripts)          |
| `-c <n>`       | Número de ciclos de prueba                                       |
| `-w`           | Modo ancho (wide), muestra más columnas                          |
| `-b`           | Muestra direcciones IP y nombres de host                         |
| `-4`           | Fuerza el uso de IPv4                                            |
| `-6`           | Fuerza el uso de IPv6                                            |
| `-p`           | Modo "split", muestra estadísticas por salto en tiempo real      |
| `-o <campos>`  | Personaliza las columnas de la salida                            |
| `-a <IP>`      | Usa una IP de origen específica                                  |

---

## 🧑‍💻 Ejemplos de uso

### 1. Diagnóstico interactivo a un dominio

```bash
mtr google.com
```

### 2. Generar un reporte en texto plano

```bash
mtr -r -c 10 8.8.8.8
```

### 3. Forzar IPv6

```bash
mtr -6 ipv6.google.com
```

### 4. Mostrar tanto IP como nombre de host

```bash
mtr -b example.com
```

---

## 📤 Salida típica

```
Start: 2025-06-02T10:00:00+0000
HOST: mi-equipo                  Loss%   Snt   Last   Avg  Best  Wrst StDev
  1.|-- 192.168.1.1              0.0%    10    1.2    1.3   1.1   1.5  0.1
  2.|-- 10.0.0.1                 0.0%    10    5.2    5.1   4.9   5.4  0.2
  3.|-- 8.8.8.8                  0.0%    10   20.3   20.1  19.8  20.5  0.2
```

- **Loss%**: Porcentaje de pérdida de paquetes en cada salto.
- **Snt**: Paquetes enviados.
- **Last/Avg/Best/Wrst**: Último, promedio, mejor y peor tiempo de respuesta (ms).
- **StDev**: Desviación estándar de la latencia.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para ciertas opciones o interfaces.
- Algunos routers pueden limitar o bloquear respuestas ICMP, afectando los resultados.
- Es ideal para detectar cuellos de botella y problemas de red intermitentes.

---

## 📚 Referencias

- [man mtr](https://man7.org/linux/man-pages/man8/mtr.8.html)
- [Wiki Arch Linux: mtr](https://wiki.archlinux.org/title/Mtr)