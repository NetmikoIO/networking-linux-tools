<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/whois.md -->

# 🌐 Comando `whois`

## 🧾 Descripción

El comando `whois` es una herramienta de línea de comandos que permite consultar bases de datos públicas para obtener información sobre la titularidad y detalles de registro de dominios, direcciones IP y redes. Es útil para identificar propietarios, fechas de expiración, servidores DNS y datos de contacto de dominios en Internet.

---

## 🧪 Sintaxis básica

```bash
whois [opciones] <dominio o IP>
```

- **dominio o IP**: Nombre de dominio (ejemplo.com) o dirección IP a consultar.

---

## ⚙️ Opciones comunes

| Opción         | Descripción                                                      |
| -------------- | ---------------------------------------------------------------- |
| `-h <servidor>`| Especifica un servidor whois diferente                            |
| `-p <puerto>`  | Especifica el puerto del servidor whois                          |
| `--verbose`    | Muestra información detallada                                    |
| `--help`       | Muestra la ayuda del comando                                     |

---

## 🧑‍💻 Ejemplos de uso

### 1. Consultar información de un dominio

```bash
whois example.com
```

### 2. Consultar información de una dirección IP

```bash
whois 8.8.8.8
```

### 3. Usar un servidor whois específico

```bash
whois -h whois.iana.org example.com
```

---

## 📤 Salida típica

```
Domain Name: EXAMPLE.COM
Registry Domain ID: 2336799_DOMAIN_COM-VRSN
Registrar WHOIS Server: whois.iana.org
Registrar URL: http://res-dom.iana.org
Updated Date: 2025-01-01T00:00:00Z
Creation Date: 1995-08-14T04:00:00Z
Registry Expiry Date: 2026-08-13T04:00:00Z
Registrar: RESERVED-Internet Assigned Numbers Authority
Name Server: A.IANA-SERVERS.NET
Name Server: B.IANA-SERVERS.NET
...
```

- **Domain Name**: Nombre del dominio consultado.
- **Registrar**: Entidad registradora del dominio.
- **Creation/Expiry Date**: Fechas de creación y expiración.
- **Name Server**: Servidores DNS asociados.
- **Contact**: Información de contacto del titular (si está disponible).

---

## ⚠️ Notas y advertencias

- La información mostrada depende del TLD y la política de privacidad del registro.
- Algunos datos pueden estar ocultos por privacidad (WHOIS privacy).
- El comando puede no estar instalado por defecto (`whois` o `jwhois`).

---

## 📚 Referencias

- [man whois](https://man7.org/linux/man-pages/man1/whois.1.html)
- [Wiki Arch Linux: whois](https://wiki.archlinux.org/title/Whois)