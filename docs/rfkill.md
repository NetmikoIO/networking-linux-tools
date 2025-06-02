<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/rfkill.md -->

# 📶 Comando `rfkill`

## 🧾 Descripción

El comando `rfkill` permite consultar, bloquear y desbloquear dispositivos de radiofrecuencia en sistemas Linux, como Wi-Fi, Bluetooth, WWAN y otros. Es útil para solucionar problemas de conectividad inalámbrica y para gestionar el acceso a radios desde la línea de comandos.

---

## 🧪 Sintaxis básica

```bash
rfkill [opciones] [comando] [id/dispositivo]
```

---

## ⚙️ Comandos y opciones comunes

| Comando/Opción         | Descripción                                                      |
|-----------------------|------------------------------------------------------------------|
| `list`                | Muestra el estado de todos los dispositivos RF                    |
| `list <id/tipo>`      | Muestra información de un dispositivo específico                  |
| `block <id/tipo>`     | Bloquea (desactiva) el dispositivo especificado                  |
| `unblock <id/tipo>`   | Desbloquea (activa) el dispositivo especificado                  |
| `soft`                | Bloqueo/desbloqueo por software                                  |
| `hard`                | Bloqueo/desbloqueo por hardware (interruptor físico)             |
| `event`               | Muestra eventos de cambio en tiempo real                          |

---

## 🧑‍💻 Ejemplos de uso

### 1. Ver el estado de todos los dispositivos RF

```bash
rfkill list
```

### 2. Bloquear el Wi-Fi

```bash
sudo rfkill block wifi
```

### 3. Desbloquear Bluetooth

```bash
sudo rfkill unblock bluetooth
```

### 4. Ver eventos de cambio en tiempo real

```bash
rfkill event
```

---

## 📤 Salida típica

```
0: phy0: Wireless LAN
	Soft blocked: no
	Hard blocked: no
1: hci0: Bluetooth
	Soft blocked: yes
	Hard blocked: no
```

- **Soft blocked**: Bloqueo por software (comando o sistema operativo).
- **Hard blocked**: Bloqueo por hardware (interruptor físico).

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para bloquear/desbloquear dispositivos.
- El bloqueo por hardware solo puede cambiarse con el interruptor físico del equipo.
- Útil para solucionar problemas cuando el Wi-Fi o Bluetooth no se activan.

---

## 📚 Referencias

- [man rfkill](https://man7.org/linux/man-pages/man8/rfkill.8.html)
- [Wiki Arch Linux: rfkill](https://wiki.archlinux.org/title/Rfkill)