<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/dig.md -->

# 🔎 Comando `dig`

## 🧾 Descripción

El comando `dig` (Domain Information Groper) es una herramienta de línea de comandos para consultar información de DNS. Permite realizar búsquedas de registros DNS de dominios, analizar la resolución de nombres y diagnosticar problemas de red relacionados con DNS. Es ampliamente utilizado por administradores de sistemas y redes.

---

## 🧪 Sintaxis básica

```bash
dig [opciones] <dominio> [tipo]
```

- **dominio**: Nombre de dominio a consultar (por ejemplo, `example.com`).
- **tipo**: Tipo de registro DNS (A, AAAA, MX, NS, TXT, etc.).

---

## ⚙️ Opciones comunes

| Opción             | Descripción                                                      |
| ------------------ | ---------------------------------------------------------------- |
| `@<servidor>`      | Especifica el servidor DNS a consultar                           |
| `+short`           | Salida breve, solo la respuesta                                  |
| `+noall +answer`   | Muestra solo la sección de respuesta                             |
| `-t <tipo>`        | Especifica el tipo de registro (A, MX, TXT, etc.)                |
| `-x <IP>`          | Realiza una consulta inversa (PTR)                               |
| `+trace`           | Traza la resolución desde la raíz DNS                            |
| `+stats`           | Muestra estadísticas de la consulta                              |
| `+nocmd`           | Oculta la línea de comando en la salida                          |

---

## 🧑‍💻 Ejemplos de uso

### 1. Consultar el registro A de un dominio

```bash
dig example.com
```

### 2. Consultar el registro MX de un dominio

```bash
dig example.com MX
```

### 3. Usar un servidor DNS específico

```bash
dig @8.8.8.8 example.com
```

### 4. Salida breve

```bash
dig example.com +short
```

### 5. Consulta inversa (PTR)

```bash
dig -x 8.8.8.8
```

### 6. Trazar la resolución DNS

```bash
dig example.com +trace
```

---

## 📤 Salida típica

```
; <<>> DiG 9.16.1-Ubuntu <<>> example.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 12345
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 2, ADDITIONAL: 3

;; QUESTION SECTION:
;example.com.            IN      A

;; ANSWER SECTION:
example.com.     3600    IN      A       93.184.216.34

;; Query time: 20 msec
;; SERVER: 8.8.8.8#53(8.8.8.8)
;; WHEN: Mon Jun  2 10:00:00 UTC 2025
;; MSG SIZE  rcvd: 65
```

- **QUESTION SECTION**: Consulta realizada.
- **ANSWER SECTION**: Respuesta del servidor DNS.
- **AUTHORITY SECTION**: Servidores autoritativos para el dominio.
- **ADDITIONAL SECTION**: Información adicional (por ejemplo, registros A de los servidores autoritativos).
- **Query time**: Tiempo de respuesta.
- **SERVER**: Servidor DNS consultado.

---

## ⚠️ Notas y advertencias

- `dig` no está instalado por defecto en todas las distribuciones; puede instalarse con el paquete `dnsutils`.
- Permite analizar problemas de propagación DNS y verificar configuraciones avanzadas.
- Para scripting, se recomienda usar la opción `+short`.

---

## 📚 Referencias

- [man dig](https://man7.org/linux/man-pages/man1/dig.1.html)
- [Wikipedia: dig](https://es.wikipedia.org/wiki/Dig)