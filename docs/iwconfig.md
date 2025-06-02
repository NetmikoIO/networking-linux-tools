<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/iwconfig.md -->

# 📡 Comando `iwconfig`

## 🧾 Descripción

El comando `iwconfig` permite ver y configurar parámetros de interfaces de red inalámbricas (Wi-Fi) en sistemas Linux. Es similar a `ifconfig`, pero enfocado en dispositivos wireless, permitiendo ajustar SSID, modo, canal, potencia, clave, y más.

> **Nota:** En sistemas modernos, `iwconfig` ha sido reemplazado en gran parte por `iw` y NetworkManager, pero sigue siendo útil para configuraciones rápidas y diagnósticos.

---

## 🧪 Sintaxis básica

```bash
iwconfig [interfaz] [opciones]
```

- **interfaz**: Nombre de la interfaz inalámbrica (por ejemplo, `wlan0`, `wlp2s0`).

---

## ⚙️ Opciones comunes

| Opción                | Descripción                                                      |
|---------------------- |-----------------------------------------------------------------|
| (sin argumentos)      | Muestra el estado de todas las interfaces wireless               |
| `<interfaz>`          | Muestra información de una interfaz específica                   |
| `essid <nombre>`      | Establece el nombre de la red (SSID)                            |
| `mode <modo>`         | Establece el modo (Managed, Ad-Hoc, Monitor, etc.)              |
| `channel <n>`         | Selecciona el canal inalámbrico                                 |
| `freq <frecuencia>`   | Selecciona la frecuencia                                        |
| `key <clave>`         | Establece la clave WEP                                          |
| `ap <MAC>`            | Fuerza la conexión a un punto de acceso específico              |
| `rate <velocidad>`    | Establece la velocidad de transmisión                           |
| `txpower <dBm>`       | Ajusta la potencia de transmisión                               |
| `power on|off`        | Activa o desactiva la gestión de energía                        |

---

## 🧑‍💻 Ejemplos de uso

### 1. Ver el estado de las interfaces inalámbricas

```bash
iwconfig
```

### 2. Conectar a una red con SSID específico

```bash
sudo iwconfig wlan0 essid "MiRedWiFi"
```

### 3. Cambiar el canal de la interfaz

```bash
sudo iwconfig wlan0 channel 6
```

### 4. Establecer clave WEP

```bash
sudo iwconfig wlan0 key s:miclavewep
```

### 5. Cambiar la potencia de transmisión

```bash
sudo iwconfig wlan0 txpower 15
```

---

## 📤 Salida típica

```
wlan0     IEEE 802.11  ESSID:"MiRedWiFi"  
          Mode:Managed  Frequency:2.437 GHz  Access Point: 00:11:22:33:44:55   
          Bit Rate=54 Mb/s   Tx-Power=15 dBm   
          Retry short limit:7   RTS thr:off   Fragment thr:off
          Power Management:off
          Link Quality=70/70  Signal level=-40 dBm  Noise level=-90 dBm
          Rx invalid nwid:0  Rx invalid crypt:0  Rx invalid frag:0
          Tx excessive retries:0  Invalid misc:0   Missed beacon:0
```

- **ESSID**: Nombre de la red Wi-Fi.
- **Mode**: Modo de operación (Managed, Ad-Hoc, etc.).
- **Frequency**: Frecuencia o canal.
- **Access Point**: MAC del punto de acceso.
- **Bit Rate**: Velocidad de transmisión.
- **Tx-Power**: Potencia de transmisión.
- **Link Quality/Signal level**: Calidad y nivel de señal.

---

## ⚠️ Notas y advertencias

- Requiere privilegios de superusuario para modificar parámetros.
- No todas las interfaces soportan todas las opciones.
- El uso de claves WEP es inseguro; se recomienda WPA2/WPA3.
- En sistemas modernos, se recomienda usar `iw` o herramientas de NetworkManager.

---

## 📚 Referencias

- [man iwconfig](https://man7.org/linux/man-pages/man8/iwconfig.8.html)
- [Wiki Arch Linux: iwconfig](https://wiki.archlinux.org/title/Iwconfig)