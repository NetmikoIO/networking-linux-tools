<!-- filepath: /home/zheiar/github/networking-linux-tools/docs/resolv.conf.md -->

# 📄 Archivo `resolv.conf`

## 🧾 Descripción

El archivo `/etc/resolv.conf` es el principal archivo de configuración de resolución de nombres DNS en sistemas Linux y Unix. Define los servidores DNS que el sistema utiliza para resolver nombres de dominio, así como opciones adicionales relacionadas con la resolución.

---

## 📂 Ubicación

- Ruta habitual: `/etc/resolv.conf`

---

## 📝 Formato y directivas principales

Cada línea contiene una directiva y su valor. Las más comunes son:

| Directiva         | Descripción                                                      |
|------------------ |-----------------------------------------------------------------|
| `nameserver`      | Especifica la IP de un servidor DNS (una por línea, hasta 3)     |
| `search`          | Lista de dominios de búsqueda para completar nombres cortos       |
| `domain`          | Dominio local predeterminado                                     |
| `options`         | Opciones avanzadas de resolución (timeout, attempts, etc.)       |

---

## 🧑‍💻 Ejemplo de contenido

```
nameserver 8.8.8.8
nameserver 1.1.1.1
search ejemplo.local miempresa.com
options timeout:2 attempts:3
```

- **nameserver**: Servidores DNS a consultar, en orden de preferencia.
- **search**: Dominios que se añaden automáticamente a las búsquedas.
- **options**: Parámetros como tiempo de espera y número de intentos.

---

## ⚠️ Notas y advertencias

- El archivo puede ser sobrescrito automáticamente por servicios como NetworkManager, `dhclient` o `systemd-resolved`.
- Para cambios persistentes, edite la configuración del gestor de red correspondiente.
- Solo usuarios con privilegios pueden modificar este archivo.
- Un error en la sintaxis puede dejar el sistema sin resolución DNS.

---

## 📚 Referencias

- [man resolv.conf](https://man7.org/linux/man-pages/man5/resolv.conf.5.html)
- [Wiki Arch Linux: resolv.conf](https://wiki.archlinux.org/title/Resolv.conf)