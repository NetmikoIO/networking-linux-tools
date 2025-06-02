<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/host.md -->

# 🌍 Comando `host`

## 🧾 Descripción

El comando `host` es una herramienta sencilla para realizar consultas DNS desde la línea de comandos. Permite obtener información sobre direcciones IP, nombres de dominio, registros específicos y realizar búsquedas inversas. Es útil para diagnósticos rápidos y verificación de la resolución de nombres.

---

## 🧪 Sintaxis básica

```bash
host [opciones] <nombre o IP> [servidor DNS]
```

- **nombre o IP**: Dominio o dirección IP a consultar.
- **servidor DNS**: (Opcional) Servidor DNS a utilizar para la consulta.

---

## ⚙️ Opciones comunes

| Opción         | Descripción                                              |
| -------------- | -------------------------------------------------------- |
| `-t <tipo>`    | Especifica el tipo de registro DNS (A, MX, TXT, etc.)   |
| `-a`           | Consulta todos los registros disponibles                 |
| `-l`           | Lista todos los subdominios de una zona (si es posible)  |
| `-v`           | Modo detallado (verbose)                                |
| `-4`           | Fuerza el uso de IPv4                                   |
| `-6`           | Fuerza el uso de IPv6                                   |

---

## 🧑‍💻 Ejemplos de uso

### 1. Consultar la IP de un dominio

```bash
host example.com
```

### 2. Consulta inversa (de IP a nombre)

```bash
host 8.8.8.8
```

### 3. Consultar un registro MX

```bash
host -t MX example.com
```

### 4. Usar un servidor DNS específico

```bash
host example.com 1.1.1.1
```

### 5. Consultar todos los registros disponibles

```bash
host -a example.com
```

---

## 📤 Salida típica

```
example.com has address 93.184.216.34
example.com mail is handled by 0 .
```

- **has address**: Dirección IP asociada al dominio.
- **mail is handled by**: Servidor de correo (registro MX).

---

## ⚠️ Notas y advertencias

- `host` es ideal para consultas rápidas, pero para análisis avanzados se recomienda `dig` o `nslookup`.
- No todas las opciones están disponibles en todas las implementaciones.
- Puede requerir el paquete `bind-utils` o `dnsutils` para estar disponible.

---

## 📚 Referencias

- [man host](https://man7.org/linux/man-pages/man1/host.1.html)
- [Wikipedia: host (Unix)](https://en.wikipedia.org/wiki/Host_(Unix))