<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/systemctl.md -->

# ⚙️ Comando `systemctl`

## 🧾 Descripción

El comando `systemctl` es la herramienta principal para gestionar servicios, unidades y el estado general del sistema en sistemas Linux que utilizan `systemd`. Permite iniciar, detener, reiniciar, habilitar, deshabilitar servicios, así como consultar el estado del sistema y administrar el arranque.

---

## 🧪 Sintaxis básica

```bash
systemctl [opciones] [comando] [unidad]
```

- **unidad**: Servicio, socket, dispositivo, montaje, etc. (por ejemplo, `nginx.service`, `sshd.service`).

---

## ⚙️ Comandos y opciones comunes

| Comando/Opción           | Descripción                                                      |
|-------------------------|------------------------------------------------------------------|
| `start <servicio>`      | Inicia un servicio                                               |
| `stop <servicio>`       | Detiene un servicio                                              |
| `restart <servicio>`    | Reinicia un servicio                                             |
| `reload <servicio>`     | Recarga la configuración de un servicio                          |
| `status <servicio>`     | Muestra el estado de un servicio                                 |
| `enable <servicio>`     | Habilita un servicio para que inicie al arrancar el sistema      |
| `disable <servicio>`    | Deshabilita el inicio automático de un servicio                  |
| `is-active <servicio>`  | Verifica si un servicio está activo                              |
| `is-enabled <servicio>` | Verifica si un servicio está habilitado                          |
| `list-units`            | Lista todas las unidades activas                                 |
| `list-unit-files`       | Lista todos los archivos de unidad                               |
| `daemon-reload`         | Recarga la configuración de systemd                              |
| `poweroff`              | Apaga el sistema                                                 |
| `reboot`                | Reinicia el sistema                                              |
| `--user`                | Gestiona servicios del usuario actual                            |

---

## 🧑‍💻 Ejemplos de uso

### 1. Iniciar, detener y reiniciar un servicio

```bash
sudo systemctl start nginx.service
sudo systemctl stop nginx.service
sudo systemctl restart nginx.service
```

### 2. Ver el estado de un servicio

```bash
systemctl status sshd.service
```

### 3. Habilitar o deshabilitar un servicio al arranque

```bash
sudo systemctl enable apache2.service
sudo systemctl disable apache2.service
```

### 4. Listar servicios activos

```bash
systemctl list-units --type=service
```

### 5. Recargar la configuración de systemd

```bash
sudo systemctl daemon-reload
```

### 6. Apagar o reiniciar el sistema

```bash
sudo systemctl poweroff
sudo systemctl reboot
```

---

## 📤 Salida típica

```
● sshd.service - OpenSSH Daemon
   Loaded: loaded (/lib/systemd/system/sshd.service; enabled)
   Active: active (running) since Mon 2025-06-02 10:00:00 UTC; 1h 23min ago
     Docs: man:sshd(8)
           man:sshd_config(5)
 Main PID: 1234 (sshd)
    Tasks: 1 (limit: 4915)
   Memory: 5.2M
   CGroup: /system.slice/sshd.service
           └─1234 /usr/sbin/sshd -D
```

- **Loaded**: Estado de carga y ruta del archivo de unidad.
- **Active**: Estado actual y tiempo de actividad.
- **Main PID**: Proceso principal del servicio.
- **CGroup**: Grupo de control asociado.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para gestionar servicios del sistema.
- Cambios en archivos de unidad requieren `daemon-reload` para aplicarse.
- `systemctl` solo está disponible en sistemas con `systemd`.

---

## 📚 Referencias

- [man systemctl](https://man7.org/linux/man-pages/man1/systemctl.1.html)
- [Wiki Arch Linux: systemctl](https://wiki.archlinux.org/title/Systemctl)