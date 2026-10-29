copilot/instalar-mx-linux-xfce-asus-k53e
# Instalación de MX Linux XFCE en un ASUS K53E

Guía completa para instalar MX Linux XFCE en un portátil ASUS K53E reemplazando Windows 10.

> **Aviso:** esta guía borra Windows 10 y todos los datos del disco. Haz copia de seguridad antes de empezar.

## Requisitos

- Portátil ASUS K53E (Intel Core i3/i5/i7 de 2.ª generación, BIOS clásica).
- Memoria USB de 4 GB o más (se borrará su contenido).
- Conexión a Internet (cable Ethernet recomendado para la primera instalación).
- Otro equipo para descargar y grabar la ISO.

## 1. Copia de seguridad

1. Copia documentos, fotos, favoritos del navegador y otros datos personales a un disco externo o a la nube.
2. Anota las licencias o claves que necesites (la clave de Windows está asociada al equipo).

## 2. Descargar MX Linux XFCE

1. Descarga la ISO de 64 bits de MX Linux XFCE desde <https://mxlinux.org/download-links/>.
2. Comprueba la suma SHA256 de la ISO con la publicada en la web:

   ```bash
   sha256sum MX-*_x64.iso
   ```

## 3. Crear el USB de instalación

- **Linux:** `sudo dd if=MX-*_x64.iso of=/dev/sdX bs=4M status=progress oflag=sync` (sustituye `/dev/sdX` por tu USB; verifícalo con `lsblk`).
- **Windows:** usa [Rufus](https://rufus.ie) en modo *imagen DD* o [balenaEtcher](https://etcher.balena.io).
- **MX Linux:** usa *MX Live USB Maker*.

## 4. Arrancar desde el USB

1. Conecta el USB y enciende el portátil pulsando **F2** para entrar en la BIOS.
2. Desactiva *Fast Boot* si está activo y, si existe, *Secure Boot*.
3. Pulsa **Esc** al arrancar para abrir el menú de arranque y elige el USB (o cambia el orden de arranque en la BIOS).
4. En el menú de MX Linux selecciona *MX-Linux* (modo Live) para probar el sistema antes de instalar.

## 5. Comprobar el hardware en modo Live

Verifica que funcionan: Wi-Fi, sonido, touchpad, webcam, brillo y teclas de función. Si el Wi-Fi no funciona, conecta por cable y consulta la sección de solución de problemas.

## 6. Instalar reemplazando Windows 10

1. Ejecuta **Instalar MX Linux** desde el escritorio Live.
2. Elige el idioma y la zona horaria.
3. En *Elegir disco* selecciona **Usar todo el disco** (borra Windows 10 por completo).
   - Para particionar manualmente: `/` (ext4, 25–40 GB), `swap` (igual a la RAM o 2–4 GB) y `/home` (resto).
4. Deja el cargador de arranque GRUB en el MBR del disco principal (`/dev/sda`).
5. Define el nombre del equipo, el usuario y las contraseñas.
6. Espera a que termine, retira el USB y reinicia.

## 7. Configuración posterior

```bash
sudo apt update && sudo apt full-upgrade -y
```

- Usa **MX Tools → MX Package Installer** para instalar controladores, códecs y programas.
- Instala microcódigo de Intel: `sudo apt install intel-microcode`.
- Gráficos Intel integrados: funcionan con el controlador libre por defecto.
- GPU NVIDIA (si la tiene): usa **MX Tools → Instalador de controladores NVIDIA**.
- Para portátiles, instala `tlp` para mejorar la batería: `sudo apt install tlp && sudo systemctl enable --now tlp`.
- Si tiene SSD, comprueba que TRIM esté activo: `systemctl status fstrim.timer`.

## Solución de problemas

| Problema | Solución |
|----------|----------|
| El USB no aparece en el menú de arranque | Vuelve a grabar la ISO en modo DD y revisa la BIOS (F2). |
| Wi-Fi no funciona | Instala el firmware con MX Package Installer (`firmware-iwlwifi`, `firmware-realtek`, `firmware-atheros`, `firmware-brcm80211`) o usa cable. |
| Pantalla negra en el arranque | En el menú de arranque pulsa **F4** y elige *nomodeset*. |
| Brillo no ajustable | Prueba el parámetro de kernel `acpi_backlight=vendor` o `acpi_osi=Linux` en GRUB. |
| No arranca tras instalar | Reinstala GRUB desde el Live con *MX Boot Repair*. |

## Licencia

Consulta el archivo [LICENSE](LICENSE).
=======
# Instalación de MX Linux XFCE en ASUS K53E

## Descripción

Guía completa para reemplazar Windows 10 por MX Linux XFCE en un portátil ASUS K53E.

## Hardware utilizado

- Modelo: ASUS K53E
- Procesador: Intel Core i5-2450M
- Memoria RAM: 4 GB
- Disco duro: 500 GB
- Sistema anterior: Windows 10
- Sistema instalado: MX Linux XFCE

## Objetivos

- Crear USB booteable con Rufus.
- Instalar MX Linux XFCE.
- Configurar Swap.
- Configurar ZRAM.
- Configurar red.
- Actualizar el sistema.
- Instalar navegadores.
- Documentar incidencias y soluciones.
- Aprender Git y GitHub.
- Utilizar Microsoft Copilot desde Linux.

---

# Índice

## Documentación

1. [Preparación](docs/01-preparacion.md)
2. [Creación del USB con Rufus](docs/02-creacion-usb-rufus.md)
3. [Instalación de MX Linux](docs/03-instalacion-mxlinux.md)
4. [Problemas y soluciones](docs/04-problemas-y-soluciones.md)
5. [Post instalación](docs/05-post-instalacion.md)
6. [Optimización ASUS K53E](docs/06-optimizacion-asus-k53e.md)
7. [Git y GitHub](docs/07-git-y-github.md)
8. [Reparación de repositorios](docs/08-reparacion-repositorios.md)

## Capturas

- [Capturas del proyecto](screenshots/README.md)

---

## Proceso realizado

### 1. Descarga de MX Linux

Versión utilizada:

```text
MX Linux XFCE x64
```

### 2. Creación del USB de instalación

Herramienta utilizada:

- Rufus

Configuración:

- Esquema: MBR
- Sistema destino: BIOS o UEFI
- Sistema de archivos: FAT32

### 3. Arranque desde USB

Teclas utilizadas:

- ESC → Menú de arranque
- F2 → BIOS

### 4. Instalación

Configuración seleccionada:

- Disco completo
- Swap: 4096 MB
- Hibernación: Activada
- ZRAM: Activado
- Samba: Activado

### 5. Problemas encontrados

#### Error de actualización

Mensaje:

```text
Sub-process /usr/bin/dpkg returned an error code (1)
```

#### Causa

La actualización se ejecutó desde la sesión Live de MX Linux.

#### Solución

Arrancar desde el disco duro instalado y ejecutar:

```bash
sudo apt update
sudo apt full-upgrade
```

#### Error de repositorios

Mensaje:

```text
Conflicting values set for option Signed-By
```

#### Causa

Existían repositorios duplicados para Google Chrome y Vivaldi.

#### Solución

Eliminar los archivos temporales:

```bash
sudo rm /etc/apt/sources.list.d/mxpitemp.sources
sudo rm /etc/apt/sources.list.d/mxtemp.list
```

Actualizar:

```bash
sudo apt update
```

---

## Estado actual

✅ MX Linux instalado

✅ Arranque desde disco duro

✅ Usuario creado

✅ Red funcionando

✅ Sistema actualizado

✅ Repositorios reparados

✅ Microsoft Edge instalado

✅ Microsoft Copilot funcionando

✅ Repositorio GitHub creado

✅ Documentación completada

⏳ Incorporación de capturas reales

---

## Autor

**Giovanni Ospina Osorio**

Correo: delta9gio@gmail.com

GitHub: https://github.com/giovospo
main
