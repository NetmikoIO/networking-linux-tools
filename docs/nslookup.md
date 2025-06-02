<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/nslookup.md -->

# 🔎 Comando `nslookup`

## 🧾 Descripción

El comando `nslookup` es una herramienta de línea de comandos para consultar servidores DNS y obtener información sobre la resolución de nombres de dominio. Permite realizar búsquedas de registros DNS, diagnósticos de red y pruebas de propagación de nombres.

---

## 🧪 Sintaxis básica

```bash
nslookup [opciones] [nombre o IP] [servidor DNS]
```

- **nombre o IP**: Dominio o dirección IP a consultar.
- **servidor DNS**: (Opcional) Servidor DNS a utilizar para la consulta.

---

## ⚙️ Opciones y comandos interactivos comunes

| Opción/Comando         | Descripción                                              |
|----------------------- |---------------------------------------------------------|
| `-type=<tipo>`         | Especifica el tipo de registro DNS (A, MX, TXT, etc.)   |
| `-debug`               | Muestra información detallada de la consulta            |
| `-timeout=<seg>`       | Establece el tiempo de espera para la respuesta         |
| `-port=<puerto>`       | Especifica el puerto del servidor DNS                   |
| `server <IP o nombre>` | Cambia el servidor DNS en modo interactivo              |
| `set q=<tipo>`         | Cambia el tipo de consulta en modo interactivo          |
| `exit`                 | Sale del modo interactivo                               |

---

## 🧑‍💻 Ejemplos de uso

### 1. Consultar la IP de un dominio

```bash
nslookup example.com
```

### 2. Consulta inversa (de IP a nombre)

```bash
nslookup 8.8.8.8
```

### 3. Consultar un registro MX usando un servidor DNS específico

```bash
nslookup -type=MX example.com 1.1.1.1
```

### 4. Usar el modo interactivo

```bash
nslookup
> server 8.8.8.8
> set q=TXT
> example.com
> exit
```

---

## 📤 Salida típica

```
Server:         8.8.8.8
Address:        8.8.8.8#53

Non-authoritative answer:
Name:   example.com
Address: 93.184.216.34
```

- **Server**: Servidor DNS consultado.
- **Address**: Dirección IP del servidor DNS.
- **Non-authoritative answer**: Respuesta obtenida (no necesariamente del servidor autoritativo).
- **Name/Address**: Dominio consultado y su IP.

---

## ⚠️ Notas y advertencias

- `nslookup` puede no estar instalado por defecto (`dnsutils` o `bind-utils`).
- Aunque sigue siendo popular, se recomienda usar `dig` o `host` para consultas avanzadas.
- Permite pruebas rápidas de resolución y propagación DNS.

---

## 📚 Referencias

- [man nslookup](https://man7.org/linux/man-pages/man1/nslookup.1.html)
- [Wiki Arch Linux: nslookup](https://wiki.archlinux.org/title/Nslookup)