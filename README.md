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
