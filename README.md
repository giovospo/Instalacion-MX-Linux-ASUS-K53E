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
