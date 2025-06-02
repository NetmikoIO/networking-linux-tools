<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/wireshark.md -->

# 🦈 Herramienta `Wireshark`

## 🧾 Descripción

Wireshark es un analizador de protocolos de red gráfico y de código abierto. Permite capturar, inspeccionar y analizar paquetes de red en tiempo real o desde archivos de captura. Es ampliamente utilizado para diagnóstico, auditoría, desarrollo y aprendizaje sobre protocolos de red.

---

## 🖥️ Características principales

- Captura y análisis de tráfico en cientos de protocolos (TCP, UDP, HTTP, DNS, etc.).
- Interfaz gráfica intuitiva con filtros avanzados.
- Soporte para múltiples formatos de captura (`.pcap`, `.pcapng`, etc.).
- Decodificación y visualización detallada de cada paquete.
- Búsqueda, seguimiento de flujos y reconstrucción de sesiones.
- Exportación de datos y estadísticas.

---

## 🧪 Uso básico

### 1. Iniciar Wireshark

- Desde el menú de aplicaciones o ejecutando en terminal:

```bash
wireshark
```

### 2. Capturar tráfico

- Selecciona la interfaz de red y haz clic en "Iniciar captura".
- Detén la captura cuando lo desees para analizar los paquetes.

### 3. Aplicar filtros de visualización

- Ejemplo: mostrar solo tráfico HTTP:

```
http
```
- Ejemplo: mostrar solo paquetes de una IP:

```
ip.addr == 192.168.1.100
```

### 4. Guardar y abrir capturas

- Archivo → Guardar como... (`.pcap`, `.pcapng`)
- Archivo → Abrir... para analizar capturas previas.

---

## ⚙️ Opciones y funciones avanzadas

- Seguimiento de flujos TCP/UDP.
- Estadísticas de protocolos, conversaciones y puntos finales.
- Decodificación de protocolos personalizados.
- Exportación de objetos (imágenes, archivos) de flujos capturados.
- Integración con herramientas como `tshark` (versión CLI).

---

## 📤 Ejemplo de análisis de paquete

Wireshark muestra cada paquete con detalles como:
- Hora de captura
- Origen y destino
- Protocolo
- Longitud
- Información detallada por capas (Ethernet, IP, TCP/UDP, aplicación)

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para capturar en la mayoría de interfaces.
- El análisis de tráfico puede exponer información sensible; úsalo con responsabilidad y ética.
- Puede instalarse con el paquete `wireshark` en la mayoría de distribuciones Linux.

---

## 📚 Referencias

- [Sitio oficial de Wireshark](https://www.wireshark.org/)
- [man wireshark](https://man7.org/linux/man-pages/man1/wireshark.1.html)
- [Wiki Arch Linux: Wireshark](https://wiki.archlinux.org/title/Wireshark)