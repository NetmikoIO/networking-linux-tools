<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/ping.md -->

# 🛰️ Comando `ping`

## 🧾 Descripción

El comando `ping` se utiliza para comprobar la conectividad de red entre el host local y otro dispositivo (local o remoto) usando el protocolo ICMP. Envía paquetes de eco y mide cuánto tarda en recibir la respuesta.

Es una herramienta **fundamental para técnicos de redes y sistemas**, ya que permite:

- Verificar si un host está activo.
- Medir latencia.
- Detectar pérdida de paquetes.
- Analizar estabilidad de la conexión.

---

## 🧪 Sintaxis básica

```bash
ping [opciones] <IP o dominio>
```

---

## ⚙️ Opciones comunes

| Opción         | Descripción                                      |
| -------------- | ------------------------------------------------ |
| `-c <n>`       | Número de paquetes a enviar                      |
| `-i <seg>`     | Intervalo entre paquetes (segundos)              |
| `-t <ttl>`     | Valor TTL (Time To Live) de los paquetes         |
| `-s <bytes>`   | Tamaño de los paquetes ICMP                      |
| `-q`           | Salida breve (solo resumen)                      |
| `-f`           | Modo flood (enviar paquetes lo más rápido posible)|
| `-W <seg>`     | Tiempo de espera por respuesta (timeout)         |
| `-4`           | Forzar uso de IPv4                               |
| `-6`           | Forzar uso de IPv6                               |

---

## 🧑‍💻 Ejemplos de uso

### 1. Hacer ping a un dominio

```bash
ping google.com
```

### 2. Enviar solo 4 paquetes

```bash
ping -c 4 8.8.8.8
```

### 3. Cambiar el intervalo entre paquetes a 2 segundos

```bash
ping -i 2 google.com
```

### 4. Forzar IPv6

```bash
ping -6 ipv6.google.com
```

### 5. Salida breve (solo resumen)

```bash
ping -c 4 -q 8.8.8.8
```

---

## 📤 Salida típica

```
PING google.com (142.250.184.206) 56(84) bytes of data.
64 bytes from 142.250.184.206: icmp_seq=1 ttl=115 time=12.3 ms
64 bytes from 142.250.184.206: icmp_seq=2 ttl=115 time=12.1 ms
64 bytes from 142.250.184.206: icmp_seq=3 ttl=115 time=12.2 ms
64 bytes from 142.250.184.206: icmp_seq=4 ttl=115 time=12.0 ms

--- google.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3004ms
rtt min/avg/max/mdev = 12.012/12.180/12.349/0.123 ms
```

- **icmp_seq**: Número de secuencia del paquete.
- **ttl**: Tiempo de vida del paquete (hops máximos).
- **time**: Latencia (ms).
- **packet loss**: Porcentaje de paquetes perdidos.
- **rtt min/avg/max/mdev**: Estadísticas de latencia.

---

## ⚠️ Notas y advertencias

- El comando puede requerir privilegios de superusuario para ciertas opciones.
- El uso excesivo de `ping` puede ser interpretado como ataque (DoS) por algunos sistemas.
- Algunos hosts pueden bloquear o limitar respuestas ICMP.

---

## 📚 Referencias

- [man ping](https://man7.org/linux/man-pages/man8/ping.8.html)
- [Wikipedia: ping](https://es.wikipedia.org/wiki/Ping)