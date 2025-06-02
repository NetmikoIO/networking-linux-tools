<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/logs.md -->

# 📝 Archivos y comandos de logs en Linux

## 🧾 Descripción

Los logs (registros) en Linux son archivos donde el sistema y las aplicaciones almacenan información sobre eventos, errores, advertencias y actividad general. Son fundamentales para el diagnóstico, auditoría y monitoreo del sistema.

---

## 📂 Ubicación de logs principales

Por convención, la mayoría de los logs se encuentran en el directorio `/var/log/`.

| Archivo/Directorio         | Descripción                                      |
|---------------------------|--------------------------------------------------|
| `/var/log/syslog`         | Registro general del sistema (Debian/Ubuntu)     |
| `/var/log/messages`       | Registro general del sistema (RedHat/CentOS)     |
| `/var/log/auth.log`       | Autenticaciones y seguridad                      |
| `/var/log/kern.log`       | Mensajes del kernel                              |
| `/var/log/dmesg`          | Mensajes de arranque y kernel                    |
| `/var/log/boot.log`       | Proceso de arranque                             |
| `/var/log/Xorg.0.log`     | Registro del servidor gráfico X                  |
| `/var/log/httpd/`         | Logs de Apache HTTP Server                       |
| `/var/log/nginx/`         | Logs de Nginx                                    |
| `/var/log/apt/`           | Logs de APT (gestor de paquetes)                 |
| `/var/log/journal/`       | Logs binarios de systemd-journald                |

---

## 🧑‍💻 Comandos útiles para ver logs

### 1. Ver el contenido de un log

```bash
cat /var/log/syslog
```

### 2. Ver las últimas líneas de un log (en tiempo real)

```bash
tail -f /var/log/syslog
```

### 3. Buscar errores en los logs

```bash
grep -i error /var/log/syslog
```

### 4. Consultar logs del sistema con journalctl (systemd)

```bash
journalctl -xe
```

### 5. Ver logs de un servicio específico

```bash
journalctl -u nombre-del-servicio
```

---

## 🛠️ Herramientas relacionadas

- `less`, `more`: Para navegar por archivos grandes.
- `zcat`, `zless`: Para ver logs comprimidos (`.gz`).
- `logrotate`: Herramienta para rotar, comprimir y gestionar logs automáticamente.
- `systemctl status <servicio>`: Muestra el estado y últimos logs de un servicio.

---

## ⚠️ Notas y advertencias

- Algunos logs requieren privilegios de superusuario para ser leídos.
- El tamaño de los logs puede crecer rápidamente; se recomienda usar `logrotate`.
- Los logs son esenciales para la seguridad y auditoría del sistema.

---

## 📚 Referencias

- [ArchWiki: Log files](https://wiki.archlinux.org/title/Log_files)
- [man journalctl](https://man7.org/linux/man-pages/man1/journalctl.1.html)
- [man logrotate](https://man7.org/linux/man-pages/man8/logrotate.8.html)