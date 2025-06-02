<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/resolvectl.md -->

# 🛠️ Comando `resolvectl`

## 🧾 Descripción

El comando `resolvectl` es una herramienta de línea de comandos para consultar y administrar la resolución de nombres DNS gestionada por `systemd-resolved` en sistemas Linux modernos. Permite ver el estado de la resolución, probar consultas DNS, ver servidores configurados y depurar problemas de red relacionados con DNS y LLMNR.

---

## 🧪 Sintaxis básica

```bash
resolvectl [comando] [argumentos]
```

---

## ⚙️ Comandos y opciones comunes

| Comando/Opción         | Descripción                                                      |
|-----------------------|------------------------------------------------------------------|
| `status`              | Muestra el estado general de la resolución DNS                   |
| `query <nombre/IP>`   | Realiza una consulta DNS o inversa                               |
| `dns <interfaz>`      | Muestra o configura los servidores DNS de una interfaz           |
| `domain <interfaz>`   | Muestra o configura los dominios de búsqueda de una interfaz     |
| `llmnr <interfaz>`    | Muestra o configura el soporte LLMNR                            |
| `mdns <interfaz>`     | Muestra o configura el soporte mDNS                             |
| `flush-caches`        | Limpia la caché de resolución DNS                               |

---

## 🧑‍💻 Ejemplos de uso

### 1. Ver el estado general de la resolución DNS

```bash
resolvectl status
```

### 2. Consultar la IP de un dominio

```bash
resolvectl query example.com
```

### 3. Consulta inversa (de IP a nombre)

```bash
resolvectl query 8.8.8.8
```

### 4. Ver los servidores DNS configurados para una interfaz

```bash
resolvectl dns eth0
```

### 5. Limpiar la caché DNS

```bash
resolvectl flush-caches
```

---

## 📤 Salida típica

```
Global
       LLMNR setting: yes
MulticastDNS setting: no
  DNSSEC setting: no
        DNSSEC supported: no
  Current DNS Server: 8.8.8.8
         DNS Servers: 8.8.8.8 1.1.1.1
          DNS Domain: ~.

Link 2 (eth0)
      Current Scopes: DNS LLMNR/IPv4 LLMNR/IPv6
DefaultRoute setting: yes
       LLMNR setting: yes
MulticastDNS setting: no
  DNSSEC setting: no
        DNS Servers: 8.8.8.8 1.1.1.1
         DNS Domain: localdomain
```

- **DNS Servers**: Servidores DNS configurados.
- **LLMNR/mDNS**: Estado de protocolos de resolución local.
- **DNSSEC**: Estado de validación de seguridad DNS.
- **Link**: Información por interfaz de red.

---

## ⚠️ Notas y advertencias

- Solo funciona en sistemas que usan `systemd-resolved`.
- Requiere privilegios para modificar la configuración de red.
- Es útil para depurar problemas de resolución DNS y ver la configuración efectiva.

---

## 📚 Referencias

- [man resolvectl](https://man7.org/linux/man-pages/man1/resolvectl.1.html)
- [Wiki Arch Linux: systemd-resolved](https://wiki.archlinux.org/title/Systemd-resolved)